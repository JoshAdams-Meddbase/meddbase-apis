---
layout: page
title: SendValidationSMS
nav_order: 3
parent: Password reset
---

# SendValidationSMS

Sends a validation code for a specific password reset key to the mobile number.

## JavaScript library method

```javascript
patientportal.passwordReset.sendValidationSMS({ key: <key> });
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| POST | `/patientportalapi/password-reset/send-validation-sms` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| is-oh | bool | True for the referral portal. False for the patient portal. |

## POST Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| key | key | The password reset key. |
