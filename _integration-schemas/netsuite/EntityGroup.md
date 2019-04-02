---
tap: "netsuite"
# version: "1.0"

name: "EntityGroup"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/EntityGroup.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "comments"
    type: "string"
    description: ""

  - name: "customFieldList"
    type: "anything"
    description: ""

  - name: "email"
    type: "string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "groupName"
    type: "string"
    description: ""

  - name: "groupOwner"
    type: "anything"
    description: ""

  - name: "groupType"
    type: "anything"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "isFunctionalTeam"
    type: "boolean, string"
    description: ""

  - name: "isInactive"
    type: "boolean, string"
    description: ""

  - name: "isManufacturingWorkCenter"
    type: "boolean, string"
    description: ""

  - name: "isPrivate"
    type: "boolean, string"
    description: ""

  - name: "isProductTeam"
    type: "boolean, string"
    description: ""

  - name: "isSalesRep"
    type: "boolean, string"
    description: ""

  - name: "isSalesTeam"
    type: "boolean, string"
    description: ""

  - name: "isSavedSearch"
    type: "boolean, string"
    description: ""

  - name: "isSupportRep"
    type: "boolean, string"
    description: ""

  - name: "issueRole"
    type: "anything"
    description: ""

  - name: "laborResources"
    type: "integer, string"
    description: ""

  - name: "machineResources"
    type: "integer, string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "parentGroupType"
    type: "anything"
    description: ""

  - name: "restrictionGroup"
    type: "anything"
    description: ""

  - name: "savedSearch"
    type: "anything"
    description: ""

  - name: "subsidiary"
    type: "anything"
    description: ""

  - name: "workCalendar"
    type: "anything"
    description: ""
---