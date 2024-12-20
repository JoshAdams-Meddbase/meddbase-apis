---
layout: page
title: ConfigData
nav_order: 22
parent: Objects and data types
---

# ConfigData

Provides informations about the current session, company and logged-in user.

## Properties

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| IsLoggedIn | bool | True if the user is logged in. |
| CompanyName | string | Name of the current company. |
| Phone | string | Official Company phone number. |
| Permissions | object | List of patient’s/user’s permissions. |
| Configuration | object | General app configuration. |
| Configuration\\SSOStatus | [SSOStatus](../objects-and-data-types/ssostatus) | Optional single sign on configuration |
| Configuration\\SessionTimeout | int | The number of seconds from the last operation the session will be active for. Use [ValidateLogin](../authentication/validatelogin) to get remaining time of the session lifetime. |
| Configuration\\ DateOfBirthRequiredForPatients | bool | True if DOB is mandatory for a patient registration. |
| ForceContactOptions | bool | Defines that the user should be forced to set up their contact options. |
| ForceTermsAndConditions | bool | Defines that the user should be forced to accept the Terms and conditions. See also [GetTermsAndConditions](../authentication/gettermsandconditions). |

## JSON Example

```json
{
    "IsLoggedIn": true,
    "CompanyName": "Test Company",
    "Phone": "077123456789",
    "Permissions": {
        "Patient": {
            "CanBookAppointment": false,
            "CanViewAppointments": false,
            "CanCancelAppointment": false,
            "CanViewInvoices": false,
            "CanPayInvoice": false,
            "CanViewMedicalHistory": false,
            "CanManageQuestionnaires": false,
            "CanManageFeeds": false,
            "CanViewCompanyLibrary": false,
            "CanViewPathways": false,
            "CanChangePassword": false
        },
        "User": {
            "CanManageUsers": true,
            "CanViewReferrals": true,
            "CanViewReferralReports": true,
            "CanReferPatient": true,
            "CanBulkReallocateReferrals": true,
            "CanViewRecall": true,
            "CanViewDocument": true,
            "CanViewAppointment": true,
            "CanChangePassword": true,
            "CanViewPathways": true
        }
    },    
    "Configuration": {
        "OnlinePaymentsEnabled": true,
        "DateOfBirthRequiredForPatients": true,
        "SSOStatus": {
            "Identifier": "shiny",
            "Enabled": true,
            "IsOH": true
        },
        "PasswordPolicy": {
            "Length": 10,
            "Numbers": 1,
            "Letters": 1,
            "NonAlphaNumeric": 0,
            "MixCaps": true,
            "Description": "at least 10 characters in length, contain at least one letter an done number and must mix upper and lower-case letters"
        },
        "DefaultCallingCode": "+44",
        "NhsConsentEnabled": false,
        "SessionTimeout": 120000,
        "DefaultPaymentCountry": "GB"
    },
    "ForceContactOptions": false,
    "ForceTermsAndConditions": false
}
```
