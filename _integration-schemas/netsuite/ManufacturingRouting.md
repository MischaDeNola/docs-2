---
tap: "netsuite"
# version: "1.0"

name: "ManufacturingRouting"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/ManufacturingRouting.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "autoCalculateLag"
    type: "boolean, string"
    description: ""

  - name: "billOfMaterials"
    type: "varies"
    description: ""

  - name: "customFieldList"
    type: "varies"
    description: ""

  - name: "customForm"
    type: "varies"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "isDefault"
    type: "boolean, string"
    description: ""

  - name: "isInactive"
    type: "boolean, string"
    description: ""

  - name: "item"
    type: "varies"
    description: ""

  - name: "locationList"
    type: "varies"
    description: ""

  - name: "memo"
    type: "string"
    description: ""

  - name: "name"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "varies"
    description: ""

  - name: "routingComponentList"
    type: "varies"
    description: ""

  - name: "routingStepList"
    type: "varies"
    description: ""

  - name: "subsidiary"
    type: "varies"
    description: ""
---
