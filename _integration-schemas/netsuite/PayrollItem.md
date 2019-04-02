---
tap: "netsuite"
# version: "1.0"

name: "PayrollItem"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/PayrollItem.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "customFieldList"
    type: "anything"
    description: ""

  - name: "employeePaid"
    type: "boolean, string"
    description: ""

  - name: "expenseAccount"
    type: "anything"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "inactive"
    type: "boolean, string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "itemType"
    type: "anything"
    description: ""

  - name: "liabilityAccount"
    type: "anything"
    description: ""

  - name: "name"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "subsidiary"
    type: "anything"
    description: ""

  - name: "vendor"
    type: "anything"
    description: ""
---