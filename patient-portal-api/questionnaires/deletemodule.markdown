---
layout: page
title: DeleteModule
nav_order: 6
parent: Questionnaires
---

# DeleteModule

Delete the specified module. The user must have the _CanModifyQuestionnaireForms_ right.

## JavaScript library method

```javascript
patientportal.questionnaires.getQuestionnaires({
    moduleKey: <module-key>
});
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| GET | `/patientportalapi/questionnaires/delete-module` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| module-key | string (required) | The key of the patient provided by the API upon [GetModules](../questionnaires/getmodules). |
