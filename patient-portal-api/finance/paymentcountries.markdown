---
layout: page
title: PaymentCountries
nav_order: 7
parent: Finance
---

# PaymentCountries

Returns a list of countries that may be used for the billing address country when making a payment.

## JavaScript library method

```javascript
patientportal.finance.prototype.getPaymentCountries()
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| GET | `/patientportalapi/payment-gateway/payment-countries` |

## Returns

[CountryData](../objects-and-data-types/countrydata)[]
