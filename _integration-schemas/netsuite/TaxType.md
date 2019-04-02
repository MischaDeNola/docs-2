---
tap: "netsuite"
# version: "1.0"

name: "TaxType"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/TaxType.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "country"
    type: "anything"
    description: ""

  - name: "description"
    type: "string"
    description: ""

  - name: "doesNotAddToTotal"
    type: "boolean, string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "isInactive"
    type: "boolean, string"
    description: ""

  - name: "name"
    type: "string"
    description: ""

  - name: "nexusAccountsList"
    type: "anything"
    description: ""

  - name: "nexusesTaxList"
    type: "anything"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "postToItemCost"
    type: "boolean, string"
    description: ""

  - name: "reverseCharge"
    type: "boolean, string"
    description: ""

  - name: "taxInNetAmount"
    type: "boolean, string"
    description: ""
---