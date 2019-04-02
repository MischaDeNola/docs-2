---
tap: "netsuite"
# version: "1.0"

name: "PhoneCall"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/PhoneCall.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "accessLevel"
    type: "boolean, string"
    description: ""

  - name: "assigned"
    type: "anything"
    description: ""

  - name: "company"
    type: "anything"
    description: ""

  - name: "completedDate"
    type: "date-time"
    description: ""

  - name: "contact"
    type: "anything"
    description: ""

  - name: "contactList"
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

  - name: "endDate"
    type: "date-time"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "lastModifiedDate"
    type: "date-time"
    description: ""

  - name: "message"
    type: "string"
    description: ""

  - name: "milestone"
    type: "anything"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "owner"
    type: "anything"
    description: ""

  - name: "phone"
    type: "string"
    description: ""

  - name: "priority"
    type: "anything"
    description: ""

  - name: "reminderMinutes"
    type: "anything"
    description: ""

  - name: "reminderType"
    type: "anything"
    description: ""

  - name: "sendEmail"
    type: "boolean, string"
    description: ""

  - name: "startDate"
    type: "date-time"
    description: ""

  - name: "status"
    type: "anything"
    description: ""

  - name: "supportCase"
    type: "anything"
    description: ""

  - name: "timeItemList"
    type: "anything"
    description: ""

  - name: "timedEvent"
    type: "boolean, string"
    description: ""

  - name: "title"
    type: "string"
    description: ""

  - name: "transaction"
    type: "anything"
    description: ""
---