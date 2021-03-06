---
title: Autopilot
permalink: /integrations/saas/autopilot
keywords: autopilot, autopilot schema, autopilot data, etl autopilot, autopilot etl
summary: "Connection instructions and schema details for Stitch's Autopilot integration."
layout: singer

# -------------------------- #
#         Tap Details        #
# -------------------------- #

name: "autopilot"
display_name: "Autopilot"

singer: true
repo-url: https://github.com/singer-io/tap-autopilot

# this-version: "1.0"

# -------------------------- #
#       Stitch Details       #
# -------------------------- #

status: "Released"
certified: false

historical: "1 year"
frequency: "60 minutes"
tier: "Free"
status-url: "http://status.autopilothq.com/"

table-selection: false
column-selection: false

anchor-scheduling: true
extraction-logs: true
loading-reports: true

# -------------------------- #
#      Setup Instructions    #
# -------------------------- #

setup-steps:
  - title: "Retrieve your Autopilot API Key"
    anchor: "retrieve-autopilot-api-key"
    content: |
      1. Sign into your Autopilot account.
      2. Click the **gear (Settings)** icon on the left side of the page.
      3. In the Settings menu, click **Autopilot API**.
      4. If you haven’t used the API before, you’ll need to generate a new key. Click the **Generate** button.
      5. Your API Key will display.

      Make sure you keep this key safe, as it has access to your Autopilot account. If at any time your key is lost or compromised, you can click the **Regenerate** button to generate a new key. **Remember to also update the key in Stitch or you'll encounter connection issues.**
  - title: "add integration"
  - title: "historical sync"
  - title: "replication frequency"

# -------------------------- #
#        Table Schemas       #
# -------------------------- #

# Looking for the table schemas & info?
# Each table has a its own .md file in /_integration-schemas/autopilot
---
{% assign integration = page %}
{% include misc/data-files.html %}
