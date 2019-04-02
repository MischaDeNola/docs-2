---
tap: "netsuite"
# version: "1.0"

name: "Usage"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/Usage.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "customForm"
    type: "anything"
    description: ""

  - name: "customer"
    type: "anything"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "item"
    type: "anything"
    description: ""

  - name: "memo"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "subscriptionPlan"
    type: "anything"
    description: ""

  - name: "usageDate"
    type: "date-time"
    description: ""

  - name: "usageQuantity"
    type: "number, string"
    description: ""

  - name: "usageSubscription"
    type: "anything"
    description: ""

  - name: "usageSubscriptionLine"
    type: "anything"
    description: ""
---