---
layout: page
title: Password reset
nav_order: 6
parent: Patient Portal API
---

# Password reset

The section helps you to reset the patient/manager password. The workflow is:

1. [SendLink](../password-reset/sendlink) asks for the password reset link to be sent via email
2. [ValidateKey](../password-reset/validatekey) validates the password reset link and tells you what kind of validation is enabled for the account (SMS vs. demographics match)
3. If SMS validation is enabled
    1. SendValidation asks for the SMS validation message to be sent
    2. [SubmitValidationCode](../password-reset/submitvalidationcode) verifies the code and establishes a session with the client
    3. [SetPassword](../password-reset/setpassword) sets the new password
4. If the demographics match is enabled (not preferred option)
    1. [\[OBSOLETE\] SetPasswordUsingDemographics](../password-reset/setpasswordusingdemographics) sets the new password

The demographics match validation is not recommended, and it is supported until all clients move to SMS validation.
