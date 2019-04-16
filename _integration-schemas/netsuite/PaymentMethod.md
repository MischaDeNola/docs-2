---
tap: "netsuite"
# version: "1.0"

name: "PaymentMethod"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/PaymentMethod.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "account"
    type: "varies"
    description: ""

  - name: "creditCard"
    type: "boolean, string"
    description: ""

  - name: "expressCheckoutArrangement"
    type: "string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "isDebitCard"
    type: "boolean, string"
    description: ""

  - name: "isInactive"
    type: "boolean, string"
    description: ""

  - name: "isOnline"
    type: "boolean, string"
    description: ""

  - name: "merchantAccountsList"
    type: "varies"
    description: ""

  - name: "name"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "varies"
    description: ""

  - name: "payPalEmailAddress"
    type: "string"
    description: ""

  - name: "undepFunds"
    type: "boolean, string"
    description: ""

  - name: "useExpressCheckout"
    type: "boolean, string"
    description: ""

  - name: "visualsList"
    type: "varies"
    description: ""
---
