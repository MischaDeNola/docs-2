---
tap: "netsuite"
# version: "1.0"

name: "CustomList"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/CustomList.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "convertToCustomRecord"
    type: "boolean, string"
    description: ""

  - name: "customValueList"
    type: "anything"
    description: ""

  - name: "description"
    type: "string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "isInactive"
    type: "boolean, string"
    description: ""

  - name: "isMatrixOption"
    type: "boolean, string"
    description: ""

  - name: "isOrdered"
    type: "boolean, string"
    description: ""

  - name: "name"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "owner"
    type: "anything"
    description: ""

  - name: "scriptId"
    type: "string"
    description: ""

  - name: "translationsList"
    type: "anything"
    description: ""
---