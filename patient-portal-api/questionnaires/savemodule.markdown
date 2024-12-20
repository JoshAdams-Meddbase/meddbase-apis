---
layout: page
title: SaveModule
nav_order: 5
parent: Questionnaires
---

# SaveModule

Create or update a module. Modules can only be shared if the logged in user has the `CanModifyQuestionnaireForms` right. Returns the key of the module created.

## JavaScript library method

```javascript
patientportal.questionnaires.saveModule({
    moduleKey: <module-key>,
    category: ’ppq’,
    moduleName: <module-name>,
    shared: <shared>,
    formKeys: <form-keys>
});
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| POST | `/patientportalapi/questionnaires/save-module` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| module-key | string (optional) | The key of the module provided by the API upon [GetModules](../questionnaires/getmodules) or a previous call to [SaveModule](../questionnaires/savemodule). If not specified, a new module will be created. |
| category | string (required) | Always ‘ppq’. |
| module-name | string (required) | Module name. |
| shared | bool (optional) | Share the module with other users. Default false. |

## POST Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| form-keys | string[] (required) | List of form keys returned from [GetQuestionnaireForms](../questionnaires/getquestionnaireforms). |

## Returned JSON

```
“ae71266c1548673052d1240115466e63a8ece5c5d3cf06abe1d006f7d975ff76”
```
