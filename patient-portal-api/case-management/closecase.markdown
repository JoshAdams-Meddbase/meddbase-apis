---
layout: page
title: CloseCase
nav_order: 4
parent: Case Management
---

# CloseCase

Closes a case and returns the newly closed case.

## JavaScript library method

```javascript
patientportal.cases.closeCase({
    case: <case>
});
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| GET | `/patientportalapi/cases/close-case` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| case | string | The key of the case. |

## Returned JSON

[CaseData](../objects-and-data-types/casedata)
