---
layout: page
title: CompanyDemographicData
nav_order: 21
parent: Objects and data types
---

# CompanyDemographicData

Contains the company’s demographic information.

## Properties

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| Code | string |     |
| Name | string |     |
| VatNo | string |     |
| Address | [AddressData](../objects-and-data-types/addressdata) |     |
| Contact | [ContactDemographicData](../objects-and-data-types/contactdemographicdata) |     |

## JSON Example

```json
{
    "CODE": "AXA",
    "Name": "AXA PPP Healthcare",
    "Address": {
        "Address1": "44 Pall Mall",
        "City": "London",
        "PostCode": "SW1Y",
        "Country": "United Kingdom"
    },
    "Contact": {
        "Title": "Mr",
        "Name": "Robert Murian",
        "Mobile": "0795523411",
        "Telephone": "+444 525 111 555",
        "EmailAddress": "<robert@comp.com>",
        "Address": {
            "Address1": "Pall Mall",
            "Address2": "",
            "Address3": "",
            "City": "London",
            "County": "",
            "PostCode": "SW1Y",
            "Country": "United Kingdom"
        }
    }
}
```
