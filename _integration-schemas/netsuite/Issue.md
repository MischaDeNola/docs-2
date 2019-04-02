---
tap: "netsuite"
# version: "1.0"

name: "Issue"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/Issue.json"
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

  - name: "brokenInVersionList"
    type: "anything"
    description: ""

  - name: "buildBroken"
    type: "anything"
    description: ""

  - name: "buildFixed"
    type: "anything"
    description: ""

  - name: "buildTarget"
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

  - name: "emailAssignee"
    type: "boolean, string"
    description: ""

  - name: "emailCellsList"
    type: "anything"
    description: ""

  - name: "emailEmployeesList"
    type: "anything"
    description: ""

  - name: "externalAbstract"
    type: "string"
    description: ""

  - name: "externalDetails"
    type: "string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "fixedInVersionList"
    type: "anything"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "isOwner"
    type: "boolean, string"
    description: ""

  - name: "isReviewed"
    type: "boolean, string"
    description: ""

  - name: "isShowStopper"
    type: "boolean, string"
    description: ""

  - name: "issueAbstract"
    type: "string"
    description: ""

  - name: "issueNumber"
    type: "string"
    description: ""

  - name: "issueStatus"
    type: "anything"
    description: ""

  - name: "issueTagsList"
    type: "anything"
    description: ""

  - name: "issueType"
    type: "anything"
    description: ""

  - name: "item"
    type: "anything"
    description: ""

  - name: "lastModifiedDate"
    type: "date-time"
    description: ""

  - name: "module"
    type: "anything"
    description: ""

  - name: "newDetails"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "priority"
    type: "anything"
    description: ""

  - name: "product"
    type: "anything"
    description: ""

  - name: "productTeam"
    type: "anything"
    description: ""

  - name: "relatedIssuesList"
    type: "anything"
    description: ""

  - name: "reportedBy"
    type: "anything"
    description: ""

  - name: "reproduce"
    type: "anything"
    description: ""

  - name: "reviewer"
    type: "anything"
    description: ""

  - name: "severity"
    type: "anything"
    description: ""

  - name: "source"
    type: "anything"
    description: ""

  - name: "targetVersionList"
    type: "anything"
    description: ""

  - name: "trackCode"
    type: "anything"
    description: ""

  - name: "versionBroken"
    type: "anything"
    description: ""

  - name: "versionFixed"
    type: "anything"
    description: ""

  - name: "versionTarget"
    type: "anything"
    description: ""
---