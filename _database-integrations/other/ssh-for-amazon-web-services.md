---
# -------------------------- #
#      Page & Formatting     #
# -------------------------- #

title: Setting up an SSH Tunnel for a database in Amazon Web Services
permalink: /common/databases/setting-up-ssh-tunnel-for-amazon-web-services
summary: ""

input: false
layout: tutorial


# -------------------------- #
#       Introduction         #
# -------------------------- #

intro: |
  {% include misc/data-files.html %}

  If a database is in a private subnet in your AWS account, you can use an SSH tunnel to connect Stitch. The approach in this tutorial will use a publicly accessible EC2 instance, or bastion, to create the connection. The bastion will act as an intermediary, forwarding the traffic from Stitch through an encrypted tunnel to the database in the private subnet.

  The approach outlined in this guide is applicable to both [integrations]({{ site.baseurl }}/integrations) (where data is extracted) and [destinations]({{ site.baseurl }}/destinations) (where data is loaded).

  Additionally, note the following before you get started:

  - **This tutorial is applicable only to Amazon Relational Database Services (RDS) databases.** Refer to [Setting up an SSH Tunnel for a database in Amazon Web Services guide]({{ link.connections.ssh-generic | prepend: site.baseurl }}) for general SSH setup instructions.

  - **An SSH tunnel isn’t necessarily more secure than a direct connection**. An SSH tunnel is only as secure as the monitoring and hardening you perform on the SSH server hosting the tunnel.

  If you have questions or concerns about Stitch security, please refer to the [Security FAQ]({{ link.account.security-faq | prepend: site.baseurl }}).


# -------------------------- #
#        Requirements        #
# -------------------------- #

requirements:
  - item: |
      **An Amazon Web Services (AWS) account.** Signing up is free - [click here](https://aws.amazon.com){:target="new"} or go to `https://aws.amazon.com` to create an account if you don't have one already.
  - item: |
      **Privileges in AWS that allow you to**:

        - **Create/manage EC2 instances.** This is required to create the SSH server.
        - **Create/manage Security Groups**. This is required to whitelist Stitch's IP addresses.
        - **View database details**. This is required to retrieve the database's connection details.


# -------------------------- #
#        Instructions        #
# -------------------------- #

steps:
  - title: "Verify the database's VPC"
    anchor: "verify-database-vpc"
    content: |
      First, you'll log into AWS and verify the Virtual Private Cloud (VPC) the database is in. The SSH bastion you'll create in Step 2 must reside in the same VPC as the database. 

      1. Log into your AWS account.
      2. Navigate to the RDS Dashboard in AWS. If you use the **Services** menu (top left corner), click the **RDS** option under the **Database** section.
      3. From the RDS Dashboard, click **Databases** on the left side of the page.
      4. On the page that displays, click the database you're connecting to Stitch. This will open the Instance Details page.
      5. Click the **Connectivity & security** tab if it's not already open.
      6. Locate the **VPC** field in the **Networking** section:

         ![The VPC field in the Instance Details page in AWS]({{ site.baseurl }}/images/integrations/amazon-rds-vpc.png)

      Keep the name of the VPC handy - you'll need it to complete the next step.

  - title: "Create a bastion in your VPC"
    anchor: "create-bastion-in-vpc"
    content: |
      In this step, you’ll launch an EC2 instance to serve as the SSH bastion. This publicly accessible instance will act as an intermediary, forwarding the traffic from Stitch through an encrypted tunnel to the database in the private subnet.

      **Note**: This instance must reside in the same VPC as the database. Refer to [Step 1](#verify-database-vpc) if you aren't sure which VPC to use.

    substeps:
      - title: "Configure the EC2 instance"
        anchor: "configure-ec2-instance"
        content: |
          The first part of creating a bastion in your VPC is configuring the instance.

          1. Navigate to the VPC Management Console in AWS. If you use the **Services** menu (top left corner), click the **VPC** option under the **Networking & Content Delivery** section.
          2. On the VPC Dashboard, click the **Launch EC2 Instances** button.
          3. Next, you’ll be asked to select the Amazon Machine Image, or AMI, that will be used to launch the instance.

             We’ll be using a Linux-based AMI (like Ubuntu) for this tutorial:

             ![Ubuntu Amazon Machine Image option in AWS]({{ site.baseurl }}/images/destinations/redshift-ssh-ubuntu-ami.png)

             Click the **Select** button next to the AMI you want to use.
          4. On the next page, you'll select the instance type. Generally, a small instance will work just fine as a bastion. For example: `t2.medium`. You can find more info about instance types on [Amazon's website](https://aws.amazon.com/ec2/instance-types/).

             After you select the instance type, click the **Configure Instance Details** button in the lower right corner of the page to continue.
          5. On the Configure Instance Details page, fill in the following fields:
             - **Network** - Select the same VPC that the database is in. Refer to [Step 1](#verify-database-vpc) if you aren't sure which VPC to use.
             - **Subnet** - Select the subnet you want to associate with the EC2 instance. This should be a **public** subnet - that is, a subnet with an Internet Gateway - as this will automatically assign a public IP address to machines in the subnet.

               If you’re not sure what subnet to use, simply leave this as the default.
             - **Auto-assign public IP** - Select **Enable** from the drop-down. This should be enabled to ensure the machine has a public IP address.

               Here's a look at our setup:

               ![Configuring the EC2 instance details]({{ site.baseurl }}/images/integrations/amazon-rds-ec2-instance-details.png)
          6. Click the **Next: Add Storage** button in the lower right corner of the page to continue.
          7. If you're only using the machine as a bastion (which is what we're doing in this tutorial), adding storage and tags are unnecessary. Skip over these pages until you reach the **Configure Security Group** page.

      - title: "Configure the EC2 instance's Security Group"
        anchor: "ec2-instance-security-group"
        content: |
          The second part of creating a bastion in your VPC is configuring the security group. During this step, you'll add Stitch's IP addresses to the security group, which will allow traffic from Stitch to access the bastion.

          You can create a **new** Security Group or update an existing one. For this tutorial, we'll create a new group.

          1. In the **Assign a security group** field, select **Create a new security group**.
          2. In the **Security group name** field, enter a unique name for the Security Group. For example: `Stitch Bastion`
          3. In the table below the **Description** field, you'll add Stitch's IP addresses to the security group:
             - **Type**: If the default SSH port for your server is 22, set this to **SSH**.

                If it’s something else, set this to **Custom TCP Rule**.
             - **Protocol**: This will default to **TCP** - leave it as-is.
             - **Port Range**: This is the number of the SSH port associated with the bastion. **If you selected SSH as the Type**, this will default to `22`.

                **If you selected Custom TCP Rule**, enter the number of the SSH port in this field.
             - **Source**: This should default to **Custom**. In the field next to the Source drop-down menu, paste one of the following IP addresses:

                {% for ip-address in ip-addresses %}
                - {{ ip-address.ip }}
                {% endfor %}

          4. Click the **Add Rule** button to add another rule.
          5. Repeat steps 3 and 4 until all of Stitch's IP addresses have been added to the Security Group.

             Here's what the Security Group rules should look like:

             ![Configuring the EC2 Instance Security Group]({{ site.baseurl }}/images/destinations/redshift-ssh-ec2-security-group.png)
          6. When finished, click the **Review and Launch** button in the lower right corner of the page.

      - title: "Review and launch the EC2 instance"
        anchor: "review-launch-ec2-instance"
        content: |
          The last step is to review the settings for the EC2 instance and launch it.

          Review the instance's settings, paying particular attention to the fields highlighted in the image below:

          ![Reviewing the EC2 Instance Details]({{ site.baseurl }}/images/integrations/amazon-rds-ec2-instance-review.png)

          - The **Security Groups** section should list either a new Security Group for Stitch OR an existing group that contains group rules for Stitch's IP addresses. If it doesn't, [refer to Step 2.2](#ec2-instance-security-group) for instructions.
          - In the **Instance Details** section:
             - **Network**: This field should contain the ID of the same VPC that the database is in.
             - **Subnet**: This field should contain the ID of a public subnet.
             - **Assign Public IP & Assign IPv6 IP:** We strongly recommend using a [public subnet with the instance](#configure-ec2-instance) and auto-assigning a public IP address. This will ensure that Stitch can access the instance.

          After you're reviewed the instance's settings, click the **Launch** button in the lower right corner to launch the instance.

          **Note**: It may take a few minutes for the instance creation process to complete. The status in the VPC Dashboard page will change to `Available` when the instance is ready.

  - title: "Enable the bastion to access the database"
    anchor: "enable-bastion-access"
    content: |
      After the EC2 instance has finished initializing, you can move onto configuring the access rules for database. In this section, you'll create a VPC Security Group that will forward traffic from the bastion (EC2 instance) to the database in the private subnet.
    
    substeps:
      - title: "Retrieve the VPC's IPv4 CIDR"
        anchor: "retrieve-vpc-ip"
        content: |
          In this step, you'll retrieve the bastion's IP address, or IPv4 CIDR. This value will be followed by a slash and a number between 0 and 32. For example: `10.0.0.0/16`

          1. Navigate to the VPC Management Console in AWS. If you use the **Services** menu (top left corner), click the **VPC** option under the **Networking & Content Delivery** section.
          2. On the VPC Dashboard, click the **Your VPCs** option under **Virtual Private Cloud** in the menu on the left side of the page.
          3. A list of all the VPCs you have access to in your AWS account will display. Locate the VPC that contains the database and the bastion.
          4. Locate the **IPv4 CIDR** column.

             If this column isn't in the table, **click on the VPC** to open its details in the bottom section of the page:

             ![VPC details & IPv4 CIDR]({{ site.baseurl }}/images/integrations/amazon-rds-vpc-ipv4-cidr.png)
          5. Copy and paste the VPC's IPv4 CIDR value somewhere convenient - you'll need it in the next step.

      - title: "Create a VPC Security Group"
        anchor: "create-vpc-security-group"
        content: |
          Now that you've retrieved the bastion's IP address, you can create a security group that will allow traffic from the bastion to access the database.

          1. From the VPC page, click the **Security Groups** option under **Security** in the menu on the left side of the page.
          2. Click the **Create Security Group** button.
          3. In the Create Security Group window:
             - **Name tag**: Enter a name tag if you want; otherwise, leave blank.
             - **Group name**: Enter `Stitch`, or a unique name for the Security Group.
             - **Description**: Enter a brief description of what the group is.
             - **VPC**: Verify that the **VPC containing the database and bastion** is selected in the drop-down.
          4. Click **Yes, Create** to create the Security Group.

      - title: "Whitelist the bastion in the VPC Security Group"
        anchor: "whitelist-bastion-vpc-security-group"
        content: |
          1. Locate and click on the Security Group you created in the previous step.
          2. In the bottom section of the page - where the Security Group's details are displayed - click the **Inbound Rules** tab.
          3. Click the **Edit** button to create an Inbound rule for the Security Group:
             - **Type:** Select **Custom TCP Rule**.
             - **Protocol**: This should default to **TCP** - leave it as-is.
             - **Port Range**: Enter the port used by the database. For example: For a PostgreSQL database, the port might be `5432`.
             - **Source**: Enter the bastion's **VPC IPv4 CIDR**. Ex: `10.0.0.0/16`

             Here's what the Inbound rule should look like:

             ![VPC inbound Security Group rule]({{ site.baseurl }}/images/destinations/redshift-ssh-vpc-security-group-rule.png)
          4. When finished, click **Save** to create the rule.


  - title: "Retrieve your Public Key"
    anchor: "retrieve-your-public-key"
    content: |
      {% include shared/retrieve-public-key.html %}

  - title: "Create the Stitch Linux user"
    anchor: "create-stitch-linux-user"
    content: |
      {% include shared/create-linux-user.html %}

  - title: "Complete the setup for Stitch"
    anchor: "complete-the-setup-for-stitch"
    content: |
      The last step is to complete the setup steps required to connect the database to Stitch. The instructions vary from database to database, and whether the database is an integration (where data is extracted) or a destination (where data is loaded).

      - If you're connecting an **integration**, locate your database in the **Integrations** list.

      - If you're connecting a **destination**, locate your database in the **Destinations** list.

      **Note**: Only Amazon-based databases are listed as this guide is only applicable to the databases listed below.

      <table class="attribute-list">
      <tr>
      <td width="50%; fixed">
      <strong>Integrations</strong>
      </td>
      <td width="50%; fixed">
      <strong>Destinations</strong>
      </td>
      </tr>
      <tr>
      <td>
      {% assign all-database-integrations = site.database-integrations | where:"input",true %}
        {% assign amazon-database-integrations = all-database-integrations | where_exp:"integration","integration.title contains 'RDS'" | sort: "title" %}

        <p>I want to extract data from:</p>

        <ul>
        {% for integration in amazon-database-integrations %}
        <li><a href="{{ integration.url }}">{{ integration.title | remove: " (v1.0)" }}</a></li>
        {% endfor %}
        </ul>
      </td>
      <td>
        {% assign rds-destinations = site.destinations | where_exp:"destination","destination.title contains 'RDS'" | sort: "title" %}

        <p>I want to load data to:</p>

        <ul>
        <li><a href="{{ link.destinations.setup.redshift | prepend: site.baseurl }}">Amazon Redshift</a></li>
        {% for destination in rds-destinations %}
        <li><a href="{{ destination.url }}">{{ destination.title | remove: "Connecting an " | remove: " Destination to Stitch" }}</a></li>
        {% endfor %}
        </ul>
      </td>
      </tr>
      </table>

---