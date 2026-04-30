---
title: "TrustKey T120"
draft: false
vendor: trustkey
vendor_link: https://www.trustkeysolutions.com/en/sub/product.form
purchase:
  amazon:
  vendor: https://www.trustkeysolutions.com/en/sub/product.form
features:
  - u2f
  - fido
  - fido-l1
  - totp
  - hotp
  - resident
  - resident-ecdsa
  - management-app
  - management-app-win
  - management-app-mac
interfaces:
  - usbc
summary: The USB-C sibling to the TrustKey T110, with FIDO2 Level 1 certification and the same OTP and resident credential support.
---

The TrustKey T120 is the USB-C version of the [T110](../trustkey-t110/). It supports OATH HOTP and TOTP through TrustKey's management application, and stores resident credentials with PIN.

The same caveats apply as the T110: the management application is required for OTP and the PIN must be set before adding SSH resident keys, otherwise the resident key registration is silently dropped.
