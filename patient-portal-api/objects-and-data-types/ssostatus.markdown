---
layout: page
title: SSOStatus
nav_order: 84
parent: Objects and data types
---

# SSOStatus

Provides information about the single sign on

## Properties

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| Identifier | string | Unique api identifier for the employer for single sign on |
| Enabled | bool | Is enabled |
| IsOh | bool | Is for referral / managers |

## JSON Example

```json
{
    "Identifier": "shiny",
    "Enabled": true,
    "IsOH": true
}
```
