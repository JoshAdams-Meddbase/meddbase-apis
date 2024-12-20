---
layout: page
title: ProvidePayment
nav_order: 4
parent: Finance
---

# ProvidePayment

Provides online payment for the patient. Loads a payment frame within the provide iframediv to process the payment. The invoice corresponding to invoice key should have the ‘PayableOnline’ parameter true (retrieved through [GetInvoiceDetail](../finance/getinvoicedetail) function.)

## JavaScript library method

```javascript
patientportal.finance.providePayment({
    invoiceKey: <invoice-key>,
    payerAccountId: <payer-accountid>,
    saveDetails: <save-payment-details>,
    description: <description>,
    iframeDiv: <iframediv>,
    firstname: <firstname>,
    surname: <surname>,
    address1: <address1>,
    address2: <address2>,
    city: <city>,
    postcode: <postcode>,
    country: <country>,
    phone: <phone>,
    email: <email>
});
```

## HTTP Method

| Verb | URL                                               |
|:-----|:--------------------------------------------------|
| POST | `/patientportalapi/payment-gateway/create-payment` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| invoice-key | int | Encrypted Key of the invoice provided by the API. |
| payer-accountid | int | Id of the existing card details for the patient retrieved using [PayerAccounts](../finance/payeraccounts). 0 if new card details are to be used. This is only valid for logged in sessions. |
| save-payment-details | bool | If the user wants to save the card details for future use, only considered if the user is logged-in. |
| description | string | Description of the payment: 100 characters |
| iframediv | string | Control id for the div to load iframe in. The javascript will load create the iframe control and append it to the provided div. |
| PayerAccountData | [PayerAccountInputData](../objects-and-data-types/payeraccountdata) | This data is not required if the system provides a valid ‘payer-account-id’. These are only used if the ‘payer-account-id’ is ‘0’. |

## Remarks

The server validates all the input parameters and if any of the validation fails, an error is returned in the ‘on fail’ call-back. On successful validation, an iframe is loaded in the provided iframediv control to process the payment, and a new callback is returned in the OnDone callback. Once the user has processed the iframe, result of payment is returned via the OnDone (if payment success) or OnFail(if payment failed) of the new callback:

Following data is included in the call-back:

OnDone:

<dl>
  <dt>Sender</dt>
  <dd>“PAYMENT-GATEWAY”</dd>
  <dt>Status</dt>
  <dd>"OK"</dd>
  <dt>StatusDetail</dt>
  <dd>Details of the payment status</dd>
  <dt>TransactionId</dt>
  <dd>Transaction id of the payment - GUID</dd>
  <dt>ClientPaymentId</dt>
  <dd>Identifier of the payment</dd>
</dl>

OnFail:

<dl>
  <dt>Sender</dt>
  <dd>“PAYMENT-GATEWAY”</dd>
  <dt>Status</dt>
  <dd>failure status</dd>
  <dt>StatusDetail</dt>
  <dd>Details of the payment failure</dd>
  <dt>TransactionId</dt>
  <dd>Transaction id of the payment - GUID</dd>
</dl>
