---
layout: page
title: GetAllowedTitles
nav_order: 8
parent: Authentication
---

# GetAllowedTitles

Gets allowed titles (for example: Mr, Mrs, etc.) that can be used within registration process.

## JavaScript library method

```javascript
patientportal.auth.getAllowedTitles({
    regCode: <reg-code>,
    membershipCode: <membership-code>,
    isOH: <is-oh>
});
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| GET | `/patientportalapi/auth/allowed-titles` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| reg-code | string (optional) | Online sign up access code that is provided to the patient. |
| membership-code | string (optional) | Membership scheme code that is provided by Medical Management Systems to the client.<br><br>See [Membership scheme](../membership-scheme/membership-scheme) |
| is-oh | bool | True for the referral portal. False for the patient portal. |

## Returns

string[]

## Remarks

One of the optional parameter reg-code or membership-code must be provided. If membership code is provided, registration code is ignored.
