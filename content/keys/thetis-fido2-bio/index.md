---
title: "Thetis BioFP FIDO2"
draft: false
vendor: thetis
vendor_link: https://thetis.io/products/fido2-fingerprint-key
purchase:
  amazon:
  vendor: https://thetis.io/products/fido2-fingerprint-key
features:
  - u2f
  - fido
  - resident
  - biometric
  - hotp
  - totp
interfaces:
  - usba
summary: Thetis' fingerprint FIDO2 key. USB-A with on device fingerprint sensor.
---

The Thetis BioFP adds an on device fingerprint sensor to the FIDO2 stack. It supports FIDO2, U2F, discoverable credentials, and OATH HOTP and TOTP. The current production unit is USB-A only.

Thetis does not produce its own management application. Fingerprint enrolment is handled through host operating system WebAuthn flows or, on Windows, through the Windows Security app.
