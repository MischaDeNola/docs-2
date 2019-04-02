---
tap: "netsuite"
version: "1.0"

name: "Customer"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/Customer.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "accessRole"
    type: "anything"
    description: ""

  - name: "accountNumber"
    type: "string"
    description: ""

  - name: "addressbookList"
    type: "anything"
    description: ""

  - name: "aging"
    type: "number, string"
    description: ""

  - name: "aging1"
    type: "number, string"
    description: ""

  - name: "aging2"
    type: "number, string"
    description: ""

  - name: "aging3"
    type: "number, string"
    description: ""

  - name: "aging4"
    type: "number, string"
    description: ""

  - name: "alcoholRecipientType"
    type: "anything"
    description: ""

  - name: "altEmail"
    type: "string"
    description: ""

  - name: "altName"
    type: "string"
    description: ""

  - name: "altPhone"
    type: "string"
    description: ""

  - name: "balance"
    type: "number, string"
    description: ""

  - name: "billPay"
    type: "boolean, string"
    description: ""

  - name: "buyingReason"
    type: "anything"
    description: ""

  - name: "buyingTimeFrame"
    type: "anything"
    description: ""

  - name: "campaignCategory"
    type: "anything"
    description: ""

  - name: "category"
    type: "anything"
    description: ""

  - name: "clickStream"
    type: "string"
    description: ""

  - name: "comments"
    type: "string"
    description: ""

  - name: "companyName"
    type: "string"
    description: ""

  - name: "consolAging"
    type: "number, string"
    description: ""

  - name: "consolAging1"
    type: "number, string"
    description: ""

  - name: "consolAging2"
    type: "number, string"
    description: ""

  - name: "consolAging3"
    type: "number, string"
    description: ""

  - name: "consolAging4"
    type: "number, string"
    description: ""

  - name: "consolBalance"
    type: "number, string"
    description: ""

  - name: "consolDaysOverdue"
    type: "integer, string"
    description: ""

  - name: "consolDepositBalance"
    type: "number, string"
    description: ""

  - name: "consolOverdueBalance"
    type: "number, string"
    description: ""

  - name: "consolUnbilledOrders"
    type: "number, string"
    description: ""

  - name: "contactRolesList"
    type: "anything"
    description: ""

  - name: "contribPct"
    type: "string"
    description: ""

  - name: "creditCardsList"
    type: "anything"
    description: ""

  - name: "creditHoldOverride"
    type: "anything"
    description: ""

  - name: "creditLimit"
    type: "number, string"
    description: ""

  - name: "currency"
    type: "anything"
    description: ""

  - name: "currencyList"
    type: "anything"
    description: ""

  - name: "customFieldList"
    type: "anything"
    description: ""

  - name: "customForm"
    type: "anything"
    description: ""

  - name: "dateCreated"
    type: "date-time"
    description: ""

  - name: "daysOverdue"
    type: "integer, string"
    description: ""

  - name: "defaultAddress"
    type: "string"
    description: ""

  - name: "defaultOrderPriority"
    type: "number, string"
    description: ""

  - name: "depositBalance"
    type: "number, string"
    description: ""

  - name: "displaySymbol"
    type: "string"
    description: ""

  - name: "downloadList"
    type: "anything"
    description: ""

  - name: "drAccount"
    type: "anything"
    description: ""

  - name: "email"
    type: "string"
    description: ""

  - name: "emailPreference"
    type: "anything"
    description: ""

  - name: "emailTransactions"
    type: "boolean, string"
    description: ""

  - name: "endDate"
    type: "date-time"
    description: ""

  - name: "entityId"
    type: "string"
    description: ""

  - name: "entityStatus"
    type: "anything"
    description: ""

  - name: "estimatedBudget"
    type: "number, string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "fax"
    type: "string"
    description: ""

  - name: "faxTransactions"
    type: "boolean, string"
    description: ""

  - name: "firstName"
    type: "string"
    description: ""

  - name: "firstVisit"
    type: "date-time"
    description: ""

  - name: "fxAccount"
    type: "anything"
    description: ""

  - name: "giveAccess"
    type: "boolean, string"
    description: ""

  - name: "globalSubscriptionStatus"
    type: "anything"
    description: ""

  - name: "groupPricingList"
    type: "anything"
    description: ""

  - name: "homePhone"
    type: "string"
    description: ""

  - name: "image"
    type: "anything"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "isBudgetApproved"
    type: "boolean, string"
    description: ""

  - name: "isInactive"
    type: "boolean, string"
    description: ""

  - name: "isPerson"
    type: "boolean, string"
    description: ""

  - name: "itemPricingList"
    type: "anything"
    description: ""

  - name: "keywords"
    type: "string"
    description: ""

  - name: "language"
    type: "anything"
    description: ""

  - name: "lastModifiedDate"
    type: "date-time"
    description: ""

  - name: "lastName"
    type: "string"
    description: ""

  - name: "lastPageVisited"
    type: "string"
    description: ""

  - name: "lastVisit"
    type: "date-time"
    description: ""

  - name: "leadSource"
    type: "anything"
    description: ""

  - name: "middleName"
    type: "string"
    description: ""

  - name: "mobilePhone"
    type: "string"
    description: ""

  - name: "monthlyClosing"
    type: "anything"
    description: ""

  - name: "negativeNumberFormat"
    type: "anything"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "numberFormat"
    type: "anything"
    description: ""

  - name: "openingBalance"
    type: "number, string"
    description: ""

  - name: "openingBalanceAccount"
    type: "anything"
    description: ""

  - name: "openingBalanceDate"
    type: "date-time"
    description: ""

  - name: "overdueBalance"
    type: "number, string"
    description: ""

  - name: "overrideCurrencyFormat"
    type: "boolean, string"
    description: ""

  - name: "parent"
    type: "anything"
    description: ""

  - name: "partner"
    type: "anything"
    description: ""

  - name: "partnersList"
    type: "anything"
    description: ""

  - name: "password"
    type: "string"
    description: ""

  - name: "password2"
    type: "string"
    description: ""

  - name: "phone"
    type: "string"
    description: ""

  - name: "phoneticName"
    type: "string"
    description: ""

  - name: "prefCCProcessor"
    type: "anything"
    description: ""

  - name: "priceLevel"
    type: "anything"
    description: ""

  - name: "printOnCheckAs"
    type: "string"
    description: ""

  - name: "printTransactions"
    type: "boolean, string"
    description: ""

  - name: "receivablesAccount"
    type: "anything"
    description: ""

  - name: "referrer"
    type: "string"
    description: ""

  - name: "reminderDays"
    type: "integer, string"
    description: ""

  - name: "representingSubsidiary"
    type: "anything"
    description: ""

  - name: "requirePwdChange"
    type: "boolean, string"
    description: ""

  - name: "resaleNumber"
    type: "string"
    description: ""

  - name: "salesGroup"
    type: "anything"
    description: ""

  - name: "salesReadiness"
    type: "anything"
    description: ""

  - name: "salesRep"
    type: "anything"
    description: ""

  - name: "salesTeamList"
    type: "anything"
    description: ""

  - name: "salutation"
    type: "string"
    description: ""

  - name: "sendEmail"
    type: "boolean, string"
    description: ""

  - name: "shipComplete"
    type: "boolean, string"
    description: ""

  - name: "shippingItem"
    type: "anything"
    description: ""

  - name: "stage"
    type: "anything"
    description: ""

  - name: "startDate"
    type: "date-time"
    description: ""

  - name: "subscriptionsList"
    type: "anything"
    description: ""

  - name: "subsidiary"
    type: "anything"
    description: ""

  - name: "symbolPlacement"
    type: "anything"
    description: ""

  - name: "syncPartnerTeams"
    type: "boolean, string"
    description: ""

  - name: "taxExempt"
    type: "boolean, string"
    description: ""

  - name: "taxItem"
    type: "anything"
    description: ""

  - name: "taxable"
    type: "boolean, string"
    description: ""

  - name: "terms"
    type: "anything"
    description: ""

  - name: "territory"
    type: "anything"
    description: ""

  - name: "thirdPartyAcct"
    type: "string"
    description: ""

  - name: "thirdPartyCountry"
    type: "anything"
    description: ""

  - name: "thirdPartyZipcode"
    type: "string"
    description: ""

  - name: "title"
    type: "string"
    description: ""

  - name: "unbilledOrders"
    type: "number, string"
    description: ""

  - name: "url"
    type: "string"
    description: ""

  - name: "vatRegNumber"
    type: "string"
    description: ""

  - name: "visits"
    type: "integer, string"
    description: ""

  - name: "webLead"
    type: "string"
    description: ""
---