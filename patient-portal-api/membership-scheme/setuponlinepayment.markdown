---
layout: page
title: SetupOnlinePayment
nav_order: 6
parent: Membership scheme
---

# SetupOnlinePayment

Sets up an online recurring payment for the current membership scheme of the patient. Loads a payment frame within the provide iframediv to process the payment. The current membership of the patient [GetCurrent](../membership-scheme/getcurrent) should have the `OnlinePaymentAllowed` parameter set and Online Payments enabled for the chamber. If the membership’s last invoice has a balance associated, the user is made to pay that invoice and the details of that transaction are used for future recurring payments. If the last invoice associated with the membership scheme does not have a balance, a penny transaction is performed which is immediately refunded. Details of this transaction are used for future recurring payments.

## JavaScript library method

```javascript
patientportal.membershipScheme.setupOnlinePayment({
    payerAccountId: <payer-accountid>,
    saveDetails: <save-payment-details>,
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
| POST | `/patientportalapi/membership-scheme/setup-online-payment` |

## URL Parameters

| Parameter | Type   | Description                                                 |
|:----------|:-------|:------------------------------------------------------------|
| payer-accountid | int | Id of the existing card details for the patient retrieved using [PayerAccounts](../finance/payeraccounts). 0 if new card details are to be used. |
| save-payment-details | bool | If the user wants to save the card details for future use. |
| iframediv | string | Control id for the div to load iframe in. The javascript will load create the iframe control and append it to the provided div. |
| PayerAccountData | [PayerAccountInputData](../objects-and-data-types/payeraccountdata) | This data is not required if the system provides a valid ‘payer-account-id’. These are only used if the ‘payer-account-id’ is ‘0’. |

## Remarks

The server validates all the input parameters and if any of the validation fails, an error is returned in the ‘on fail’ call-back. On successful validation, an iframe is loaded in the provided iframediv control to process the payment, and a new callback is returned in the OnDone callback. Once the user has processed the iframe, result of payment is returned via the OnDone (if payment success) or OnFail (if payment failed) of the new callback:

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
