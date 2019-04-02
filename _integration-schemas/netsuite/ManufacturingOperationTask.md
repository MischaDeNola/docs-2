---
tap: "netsuite"
# version: "1.0"

name: "ManufacturingOperationTask"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/ManufacturingOperationTask.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "actualWork"
    type: "number, string"
    description: ""

  - name: "autoCalculateLag"
    type: "boolean, string"
    description: ""

  - name: "completedQuantity"
    type: "number, string"
    description: ""

  - name: "costDetailList"
    type: "anything"
    description: ""

  - name: "customFieldList"
    type: "anything"
    description: ""

  - name: "customForm"
    type: "anything"
    description: ""

  - name: "endDate"
    type: "date-time"
    description: ""

  - name: "estimatedWork"
    type: "number, string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "inputQuantity"
    type: "number, string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "laborResources"
    type: "integer, string"
    description: ""

  - name: "machineResources"
    type: "integer, string"
    description: ""

  - name: "manufacturingCostTemplate"
    type: "anything"
    description: ""

  - name: "manufacturingWorkCenter"
    type: "anything"
    description: ""

  - name: "message"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "operationSequence"
    type: "integer, string"
    description: ""

  - name: "order"
    type: "anything"
    description: ""

  - name: "predecessorList"
    type: "anything"
    description: ""

  - name: "remainingWork"
    type: "number, string"
    description: ""

  - name: "runRate"
    type: "number, string"
    description: ""

  - name: "setupTime"
    type: "number, string"
    description: ""

  - name: "startDate"
    type: "date-time"
    description: ""

  - name: "status"
    type: "anything"
    description: ""

  - name: "title"
    type: "string"
    description: ""

  - name: "workOrder"
    type: "anything"
    description: ""
---