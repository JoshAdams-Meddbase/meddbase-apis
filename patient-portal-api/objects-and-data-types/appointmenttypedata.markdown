---
layout: page
title: AppointmentTypeData
nav_order: 11
parent: Objects and data types
---

# AppointmentTypeData

Type of the appointment.

## Properties

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| Key | string |     |
| Name | string |     |
| Notes | string |     |
| CancellationPolicy | string | The cancellation policy message. This cancellation policy will apply within cancellation the existing appointment.<br><br>Use the [GetAppointmentCancellationInfo](../appointments/getappointmentcancellationinfo) to retrieve exact cancellation message and fee for the concrete appointment at certain time. |
| Modules | [AppointmentModuleData](../objects-and-data-types/appointmentmoduledata)[] | Possible modules for the appointment type. If no modules are provided the appointment type doesn’t contains modules. |
| CanBookAppointment | bool | Defines whether the logged in patient is allowed to book an appointment for this appointment type. |
| CanReferPatient | bool | Defines whether the logged in patient is allowed to refer patient for this appointment type. |
| TelemedicineOption | bool | Defines whether the appointment IS booked as a telemedicine appointment or not. |
| CanAddServices | bool | Defines whether the appointment type allows adding of additional services besides appointment modules. |

## JSON Example

```json
{
    "Key": "CN",
    "Name": "Consultation",
    "CancellationPolicy": "You will be charged at 50% of the full price if you cancel the appointment within 72 hours. You will be charged at 90% of the full price if you do not turn up.",
    "CanBookAppointment": true,
    "CanReferPatient": false,
    "TelemedicineOption": true,
    "CanAddServices": false
}
```
