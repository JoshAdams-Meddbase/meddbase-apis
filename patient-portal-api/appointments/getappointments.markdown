---
layout: page
title: GetAppointments
nav_order: 10
parent: Appointments
---

# GetAppointments

Gets the patient’s appointments.

## JavaScript library method

```javascript
patientportal.appointment.getAppointments({
    patient: <patient>,
    appointmentTypeName: <appointment-type-name>,
    startFrom: <start-from>,
    startTo: <start-to>,
    case: <case>,
    pageSortColumn: <page-sort-column>,
    pageSortDescending: <page-sort-descending>,
    pageNumber: <page-number>,
    pageSize: <page-size>
});
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| GET | `/patientportalapi/appointment/appointments` |

## URL Parameters

<table>
    <thead>
        <tr>
            <th style="text-align: left">Parameter</th>
            <th style="text-align: left">Type</th>
            <th style="text-align: left">Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>patient</td>
            <td>string (optional)</td>
            <td>
                <p>The key of the patient provided by the API upon section <a href="../patients/patients">Patients</a>.</p>
                <p>Default is undefined which returns appointments for all patients.</p>
            </td>
        </tr>
        <tr>
            <td>appointment-type-name</td>
            <td>string (optional)</td>
            <td>The appointment type name filter.</td>
        </tr>
        <tr>
            <td>start-from</td>
            <td>DateTime (optional)</td>
            <td>The appointment start date filter.</td>
        </tr>
        <tr>
            <td>start-to</td>
            <td>DateTime (optional)</td>
            <td>The appointment start date filter.</td>
        </tr>
        <tr>
            <td>case</td>
            <td>int (optional)</td>
            <td>The case key for the appointment.</td>
        </tr>
        <tr>
            <td>page-sort-column</td>
            <td>int (optional)</td>
            <td>
                <p>The column index to sort the result:</p>
                <ul>
                    <li>0 –Start date</li>
                    <li>1 – Appointment type name</li>
                </ul>
                <p>Default: 0</p>
            </td>
        </tr>
        <tr>
            <td>page-sort-descending</td>
            <td>int (optional)</td>
            <td>True to sort result descending. Default false.</td>
        </tr>
        <tr>
            <td>page-number</td>
            <td>int (optional)</td>
            <td>Required page number. Default 1.</td>
        </tr>
        <tr>
            <td>page-size</td>
            <td>int (optional)</td>
            <td>Required page size. Default 10. Minimum 5. Maximum 50.</td>
        </tr>
    </tbody>
</table>

## Returns

[AppointmentData](../objects-and-data-types/appointmentdata)[]

## Returned JSON

```json
{
    "Items": [
        {
            "Key": "apt58462",
            "Type": {
                "Key": "CN",
                "Name": "Consultation"
            },
            "Start": "2013-08-07T09:30:00",
            "Finish": "2013-08-07T10:30:00",
            "Telemedicine": true,
            "TelemedicineConnection": "http://Meddbase.sandboxga.com/flex.html?roomdirect.html&key=Wchof474qrCO2QLrNK1SEMdrRY",
            "AuthorisationCode": "ABC123",
            "Site": {
                "Key": 1123,
                "Name": "2CP (Eye Room)",
                "Address": {
                    "Address1": "2 Clifton Park Ave",
                    "Address2": "",
                    "Address3": "",
                    "City": "London",
                    "County": "",
                    "PostCode": "SW20 8BD",
                    "Country": "United Kingdom"
                }
            },
            "Location": {
                "Key": 214,
                "Name": "Room 1",
                "Address": {
                    "Address1": "2 Clifton Park Ave",
                    "Address2": "",
                    "Address3": "",
                    "City": "London",
                    "County": "",
                    "PostCode": "SW20 8BD",
                    "Country": "United Kingdom"
                }
            },
            "Clinician": {
                "Key": 84,
                "Name": "Dr. House"
            },
            "Slots": [
                {
                    "Type": "CN",
                    "Start": "2013-08-07T09:30:00",
                    "Finish": "2013-08-07T10:30:00",
                    "SiteKey": 1123,
                    "LocationKey": 214,
                    "ResourceKey": 468
                }
            ],
            "PrimaryAttendeeSlot": {
                "Type": "CN",
                "Start": "2013-08-07T09:30:00",
                "Finish": "2013-08-07T10:30:00",
                "SiteKey": 1123,
                "LocationKey": 214,
                "ResourceKey": 468
            },
            "Invoice": {
                "Key": "inv4645",
                "Date": "2013-02-06",
                "Number": "1865",
                "CurrencyCode": "GBP",
                "CurrencySymbol": "£",
                "TotalNet": 200,
                "Tax": 40,
                "TotalGross": 240,
                "Paid": 150,
                "Creditor": {
                    "Name": "AXA PPP Healthcare",
                    "IsCompany": true,
                    "Address": {
                        "Address1": "44 Pall Mall",
                        "City": "London",
                        "PostCode": "SW1Y",
                        "Country": "United Kingdom"
                    },
                    "Account": {
                        "CODE": "AXA",
                        "Name": "AXA PPP Healthcare",
                        "Address": {
                            "Address1": "44 Pall Mall",
                            "City": "London",
                            "PostCode": "SW1Y",
                            "Country": "United Kingdom"
                        }
                    }
                },
                "Debtor": {
                    "Name": "Mr. John Lemon",
                    "IsCompany": false,
                    "Address": {
                        "Address1": "Studio 99",
                        "Address2": "Backlok Street",
                        "Address3": "Camden",
                        "City": "London",
                        "County": "",
                        "PostCode": "N1 7NK",
                        "Country": "United Kingdom"
                    },
                    "Account": {
                        "Title": "Mr",
                        "Name": "John",
                        "Surname": "Lemon",
                        "SexType": 1,
                        "Initials": "JL",
                        "DateOfBirth": "1958-08-02T00:00:00",
                        "Mobile": "+444 895 523 411",
                        "Telephone": "+444 525 111 555",
                        "EmailAddress": "<john.lemon@test.com>",
                        "Address": {
                            "Address1": "Studio 99",
                            "Address2": "Backlok Street",
                            "Address3": "Camden",
                            "City": "London",
                            "County": "",
                            "PostCode": "N1 7NK",
                            "Country": "United Kingdom"
                        }
                    }
                },
                "PayableOnline": true
            }
        }
    ],
    "TotalCount":1,
    "CurrentPage":1,
    "PageSize":10,
    "SortColumn": 0,
    "SortDescending": false
}
```
