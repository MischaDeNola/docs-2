---
tap: "netsuite"
# version: "1.0"

name: "SupportCase"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/SupportCase.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "assigned"
    type: "anything"
    description: ""

  - name: "caseNumber"
    type: "string"
    description: ""

  - name: "category"
    type: "anything"
    description: ""

  - name: "company"
    type: "anything"
    description: ""

  - name: "contact"
    type: "anything"
    description: ""

  - name: "createdDate"
    type: "date-time"
    description: ""

  - name: "customFieldList"
    type: "anything"
    description: ""

  - name: "customForm"
    type: "anything"
    description: ""

  - name: "email"
    type: "string"
    description: ""

  - name: "emailEmployeesList"
    type: "anything"
    description: ""

  - name: "emailForm"
    type: "boolean, string"
    description: ""

  - name: "endDate"
    type: "date-time"
    description: ""

  - name: "escalateToList"
    type: "anything"
    description: ""

  - name: "escalationMessage"
    type: "string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "helpDesk"
    type: "boolean, string"
    description: ""

  - name: "inboundEmail"
    type: "string"
    description: ""

  - name: "incomingMessage"
    type: "string"
    description: ""

  - name: "insertSolution"
    type: "anything"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "internalOnly"
    type: "boolean, string"
    description: ""

  - name: "isInactive"
    type: "boolean, string"
    description: ""

  - name: "issue"
    type: "anything"
    description: ""

  - name: "item"
    type: "anything"
    description: ""

  - name: "lastMessageDate"
    type: "date-time"
    description: ""

  - name: "lastModifiedDate"
    type: "date-time"
    description: ""

  - name: "lastReopenedDate"
    type: "date-time"
    description: ""

  - name: "module"
    type: "anything"
    description: ""

  - name: "newSolutionFromMsg"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "origin"
    type: "anything"
    description: ""

  - name: "outgoingMessage"
    type: "string"
    description: ""

  - name: "phone"
    type: "string"
    description: ""

  - name: "priority"
    type: "anything"
    description: ""

  - name: "product"
    type: "anything"
    description: ""

  - name: "profile"
    type: "anything"
    description: ""

  - name: "searchSolution"
    type: "string"
    description: ""

  - name: "serialNumber"
    type: "anything"
    description: ""

  - name: "solutionsList"
    type: "anything"
    description: ""

  - name: "startDate"
    type: "date-time"
    description: ""

  - name: "status"
    type: "anything"
    description: ""

  - name: "subsidiary"
    type: "anything"
    description: ""

  - name: "timeItemList"
    type: "anything"
    description: ""

  - name: "title"
    type: "string"
    description: ""
---