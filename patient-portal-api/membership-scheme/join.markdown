---
layout: page
title: Join
nav_order: 5
parent: Membership scheme
---

# Join

Joins the patient into the membership scheme.

## JavaScript library method

```javascript
patientportal.membershipScheme.join({code: <code>});
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| GET | `/patientportalapi/membership-scheme/join` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| code | string | Membership scheme code that is provided by Medical Management Systems to the client. |

## Remarks

If the patient is joined successfully then the HTTP status code is 2xx. Otherwise check the exception (see [Error handling](../error-handling/error-handling)).
