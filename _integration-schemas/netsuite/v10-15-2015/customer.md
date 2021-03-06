--- 
tap: "netsuite" 
version: "10-15-2015" 

name: "netsuite_customer"  
doc-link: https://system.netsuite.com/help/helpcenter/en_US/srbrowser/Browser2016_1/schema/search/customersearchbasic.html?mode=package 
description: |
  The `{{ table.name }}` table contains info about customers. 
replication-method: "Key-based Incremental"  
abstract: false 

permissions: 
  - name: "Customer Profile"  
    level: "View" 
    location: "Lists" 

attributes:  
  - name: "internalId"  
    type: "integer" 
    primary-key: true 
    description: |  
      The customer ID. 

  - name: "lastModifiedDate" 
    type: "date-time" 
    replication-key: true 
    description: |
      The time the customer was last updated.

  - name: "Additional fields"  
    description: |
      For a list of available attributes, refer to [{{ integration.display_name }}'s documentation]({{ table.doc-link }}){:target="new"}. **Note**: You will need to log into your {{ integration.display_name }} account to view the documentation.
---