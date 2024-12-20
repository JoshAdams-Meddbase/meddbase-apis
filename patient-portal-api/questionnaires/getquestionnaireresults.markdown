---
layout: page
title: GetQuestionnaireResults
nav_order: 4
parent: Questionnaires
---

# GetQuestionnaireResults

Get the results of a questionnaire request. The result of this call is an array of result objects, one for each questionnaire in the request. Each result has the HTML markup of a results document created from the answers.

## JavaScript library method

```javascript
patientportal.questionnaires.getQuestionnaireResults({
    questionnaireRequest: <questionnaire-request>
});
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| GET | `/patientportalapi/questionnaires/results` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| questionnaire-request | string | The key of the questionnaire request returned by [CreateRequest](../questionnaires/createrequest) or [GetQuestionnaires](../questionnaires/getquestionnaires) |

## Returns

[QuestionnaireResultData](../objects-and-data-types/questionnaireresultdata)[]
