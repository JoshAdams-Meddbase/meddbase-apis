---
layout: page
title: BookProposedAppointment
nav_order: 8
parent: Appointments
---

# BookProposedAppointment

Books and returns the new appointment. Returned appointment contains the amount owned by the patient.

## JavaScript library method

```javascript
patientportal.appointment.bookProposedAppointment({
    proposedAppointment: <proposedAppointment> ,
    patient: <patient>,
    referral: <referral>,
    recall: <recall>
});
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| POST | `/patientportalapi/appointment/book` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| patient | string (optional) | The key of the patient provided by the API upon section [Patients](../patients/patients).<br><br>Used to book an appointment for a different patient within your company. Default is the logged in patient. |
| referral | string (optional) | The key of the referral provided by the API upon [GetReferrals](../referrals/getreferrals).<br><br>Used to book an appointment for a specific referral. |
| recall | string (optional) | The key of the recall provided by the API upon method [GetRecalls](../recalls/getrecalls).<br><br>Used to book an appointment for a specific recall. |

## POST Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| proposedAppointment | AppointmentData | The proposed appointment provided by the API upon [GetProposedAppointments](../appointments/getproposedappointments). |

## Returns

[AppointmentData](../objects-and-data-types/appointmentdata)

## Remarks

If the appropriate appointment is taken by another user in the meantime then an exception is thrown. See [Error handling](../error-handling/error-handling). If the response contains the invoice the client use the invoice number and unpaid part of invoice to provide payment.
