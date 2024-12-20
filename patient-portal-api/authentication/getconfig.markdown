---
layout: page
title: GetConfig
nav_order: 24
parent: Authentication
---

# GetConfig

Returns the chamber basic information and the permissions of the currently logged in user has.

## JavaScript library method

```javascript
patientportal.auth.getConfig({
    companyIdentifier: <company-identifier>
});
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| GET | `/patientportalapi/auth/config` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| company-identifier | string (optional) | Unique ‘api-identifier’ for employer’s single sign on. If the user is not logged in, this returns as a part of configuration, if single sign on is available for the employer corresponding to the unique identifier. If user is logged in, this is ignored and instead the single sign on information for the logged in user is returned. |

## Returns

[ConfigData](../objects-and-data-types/configdata)
