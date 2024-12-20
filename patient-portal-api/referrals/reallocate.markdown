---
layout: page
title: Reallocate
nav_order: 9
parent: Referrals
---

# Reallocate

Re-allocate the referral to another user.

## JavaScript library method

```javascript
patientportal.referrals.reallocate({
    referral: <referral>,
    user: <user>
});
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| GET | `/patientportalapi/referrals/reallocate` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| referral | string | The key of the referral provided by the API upon [GetReferrals](../referrals/getreferrals). |
| user | string | The key of the user provided by the API upon [FindUserToReallocate](../referrals/findusertoreallocate). |

## Returns

[ReferralData](../objects-and-data-types/referraldata)
