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
    type: "varies"
    description: ""

  - name: "company"
    type: "varies"
    description: ""

  - name: "completedDate"
    type: "date-time"
    description: ""

  - name: "contact"
    type: "varies"
    description: ""

  - name: "contactList"
    type: "varies"
    description: ""

  - name: "createdDate"
    type: "date-time"
    description: ""

  - name: "customFieldList"
    type: "varies"
    description: ""

  - name: "customForm"
    type: "varies"
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
    type: "varies"
    description: ""

  - name: "nullFieldList"
    type: "varies"
    description: ""

  - name: "owner"
    type: "varies"
    description: ""

  - name: "phone"
    type: "string"
    description: ""

  - name: "priority"
    type: "varies"
    description: ""

  - name: "reminderMinutes"
    type: "varies"
    description: ""

  - name: "reminderType"
    type: "varies"
    description: ""

  - name: "sendEmail"
    type: "boolean, string"
    description: ""

  - name: "startDate"
    type: "date-time"
    description: ""

  - name: "status"
    type: "varies"
    description: ""

  - name: "supportCase"
    type: "varies"
    description: ""

  - name: "timeItemList"
    type: "varies"
    description: ""

  - name: "timedEvent"
    type: "boolean, string"
    description: ""

  - name: "title"
    type: "string"
    description: ""

  - name: "transaction"
    type: "varies"
    description: ""
---
