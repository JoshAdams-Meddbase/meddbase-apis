---
layout: page
title: AbsenceData
nav_order: 1
parent: Objects and data types
---

# AbsenceData

A full absence record data object which includes full patient demographic data.

## Properties

<table><tbody><tr><th colspan="2"><p>Key</p></th><th colspan="2"><p>string</p></th><th><p>The key of the absence record.</p></th></tr><tr><td colspan="2"><p>Patient</p></td><td colspan="2"><p><a href="../objects-and-data-types/persondemographicdata">PatientDemographicData</a></p></td><td><p>The patient’s demographic details.</p></td></tr><tr><td colspan="2"><p>StartDate</p></td><td colspan="2"><p><a href="../objects-and-data-types/datetime">DateTime</a></p></td><td><p>The date that the absence started.</p></td></tr><tr><td colspan="2"><p>EstimatedEndDate</p></td><td colspan="2"><p><a href="../objects-and-data-types/datetime">DateTime</a></p></td><td><p>The estimated return-to-work date.</p></td></tr><tr><td colspan="2"><p>EndDate</p></td><td colspan="2"><p><a href="../objects-and-data-types/datetime">DateTime</a> (optional)</p></td><td><p>The actual return-to-work date.</p></td></tr><tr><td colspan="2"><p>AbsenceStatusCode</p></td><td colspan="2"><p>int</p></td><td><p>The status code of the absence record.</p><ul><li>0 – Open</li><li>1 – Deleted</li><li>2– Closed</li></ul></td></tr><tr><td colspan="2"><p>AbsenceStatusName</p></td><td colspan="2"><p>string</p></td><td><p>The name of the status code of the absence record, as specified in the AbsenceStatusCode.</p></td></tr><tr><td colspan="2"><p>QuestionnaireStatusCode</p></td><td colspan="2"><p>int</p></td><td><p>The status code of the absence.</p><ul><li>0 – Not Sent</li><li>1 – Sent</li><li>2– Completed</li></ul></td></tr><tr><td><p>QuestionnaireStatusName</p></td><td colspan="2"><p>string</p></td><td colspan="2"><p>The name of the status code of the absence record’s questionnaire request, as specified in the QuestionnaireStatusCode.</p></td></tr><tr><td colspan="2"><p>LostWork</p></td><td colspan="2"><p><a href="../objects-and-data-types/lostwork">LostWork</a></p></td><td><p>The details about the amount of work lost due to the absence.</p></td></tr><tr><td colspan="2"><p>Reason</p></td><td colspan="2"><p>string</p></td><td><p>The name of the reason for the absence.</p></td></tr><tr><td colspan="2"><p>AccidentAtWork</p></td><td colspan="2"><p>bool</p></td><td><p>Whether the absence was a result of an accident in the workplace.</p></td></tr><tr><td colspan="2"><p>ReasonSharedWithEmployer</p></td><td colspan="2"><p>bool</p></td><td><p>Whether the reason for the absence is to be shared with the employer.</p></td></tr></tbody></table>

## JSON Example

```json
{
    "Patient": {
        "Title": "Mr",
        "Name": "John",
        "Surname": "Lemon",
        "SexType": 1,
        "Initials": "JL",
        "DateOfBirth": "1958-08-02T00:00:00",
        "Mobile": "+444 895 523 411",
        "Telephone": "+444 525 111 555",
        "EmailAddress": "<john.lemon@test.com>",
        "WorkEmailAddress": "<john.lemon@mywork.com>",
        "Address": {
            "Address1": "Studio 99",
            "Address2": "Backlok Street",
            "Address3": "Camden",
            "City": "London",
            "County": "",
            "PostCode": "N1 7NK",
            "Country": "United Kingdom"
        }
    },
    "Key": "efdc81efac0fd1a7f7b1833697a3ec3b",
    "StartDate": "2018-06-11T00:00:00",
    "EstimatedEndDate": "2018-06-15T00:00:00",
    "EndDate": "2018-06-15T00:00:00",
    "AbsenceStatusCode": 2,
    "AbsenceStatusName": "Closed",
    "QuestionnaireStatusCode": 0,
    "QuestionnaireStatusName": "Not sent",
    "LostWork": {
        "Hours": 32,
        "Days": 4
    },
    "Reason": "Brain Tumour",
    "AccidentAtWork": false,
    "ReasonSharedWithEmployer": true
}
```
