---
layout: page
title: PatientReportReviewState
nav_order: 60
parent: Objects and data types
---

# PatientReportReviewState

Provides information about the state of the patient medical report review.

## Properties

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| Required | bool | True if the patient requires the medical report review. |
| InProgress | bool | True if the review is in progress (i.e. an invitation email has been sent to the patient). |
| Finished | bool | True if the review has been finished. |
| State | string | The current state of the review. |
| StartDate | [DateTime](../objects-and-data-types/datetime) (optional) | The review start date and time. |
| PatientFirstAttempt | [DateTime](../objects-and-data-types/datetime) (optional) | The time of the patient’s first attempt to read the report. |

## JSON Examples

```json
{
    "Required": true,
    "InProgress": false,
    "Finished": false,
    "State": "Not started"
}
```

Or

```json
{
    "Required": true,
    "InProgress": false,
    "Finished": true,
    "State": "Refused",
    "StartDate": "2016-11-23T08:00:01.483",
    "PatientFirstAttempt": "2016-11-23T14:22:12.483"
}
```
