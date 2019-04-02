---
tap: "netsuite"
# version: "1.0"

name: "Message"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/Message.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "activity"
    type: "anything"
    description: ""

  - name: "author"
    type: "anything"
    description: ""

  - name: "authorEmail"
    type: "string"
    description: ""

  - name: "bcc"
    type: "string"
    description: ""

  - name: "cc"
    type: "string"
    description: ""

  - name: "compressAttachments"
    type: "boolean, string"
    description: ""

  - name: "dateTime"
    type: "string"
    description: ""

  - name: "emailed"
    type: "boolean, string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "incoming"
    type: "boolean, string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "lastModifiedDate"
    type: "date-time"
    description: ""

  - name: "mediaItemList"
    type: "anything"
    description: ""

  - name: "message"
    type: "string"
    description: ""

  - name: "messageDate"
    type: "date-time"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "recipient"
    type: "anything"
    description: ""

  - name: "recipientEmail"
    type: "string"
    description: ""

  - name: "recordName"
    type: "string"
    description: ""

  - name: "recordTypeName"
    type: "string"
    description: ""

  - name: "subject"
    type: "string"
    description: ""

  - name: "transaction"
    type: "anything"
    description: ""
---