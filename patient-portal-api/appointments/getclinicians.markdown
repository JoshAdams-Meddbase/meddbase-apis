---
layout: page
title: GetClinicians
nav_order: 6
parent: Appointments
---

# GetClinicians

Gets possible clinicians/doctors for the specific appointment type.

## JavaScript library method

```javascript
patientportal.appointment.getClinicians({
    appointmentType: <appointment-type>,
    sites: <sites>,
    locations: <locations>,
    payerType: <payer-type>,
    patient: <patient>,
    referral: <referral>,
    recall: <recall>
});
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| POST | `/patientportalapi/appointment/clinicians` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| appointment-type | string | Type of the appointment provided by the API upon [GetAppointmentTypes](../appointments/getappointmenttypes). |
| payer-type | string | Type of the payer provided by the API upon [GetPayerTypes](../appointments/getpayertypes). |
| patient | string (optional) | The key of the patient provided by the API upon section [Patients](../patients/patients).<br><br>Used to book an appointment for a different patient within your company. Default is the logged in patient. |
| referral | string (optional) | The key of the referral provided by the API upon [GetReferrals](../referrals/getreferrals).<br><br>Used to book an appointment for a specific referral. |
| recall | string (optional) | The key of the recall provided by the API upon method [GetRecalls](../recalls/getrecalls).<br><br>Used to book an appointment for a specific recall. |

## POST Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| sites | int[] (optional) | Sites filter. Array of identifiers provide by the API upon [GetSites](../appointments/getsites).<br><br>Null or empty for any sites. |
| locations | int[] (optional) | Locations filter. Array of identifiers provide by the API upon [GetSites](../appointments/getsites).<br><br>Null or empty for any locations. |
| modules | [AppointmentModuleData](../objects-and-data-types/appointmentmoduledata)[] (optional) | Selection of modules and additional services provided by the API upon [GetAppointmentTypes](../appointments/getappointmenttypes). Available clinicians will be filtered according to availability of the specified modules. |

## Returns

[ClinicianData](../objects-and-data-types/cliniciandata)[]
