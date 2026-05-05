---
title: "Token2 PIN+ Release 2 (legacy)"
draft: false
vendor: token2
vendor_link: https://www.token2.com/shop/category/pin-plus-series
deprecated: true
purchase:
  amazon:
  vendor: https://www.token2.com/shop/category/pin-plus-series
features:
  - u2f
  - fido
  - resident
  - resident-ecdsa
  - hotp
  - totp
interfaces:
  - usba
  - usbc
summary: The original PIN+ release. Now superseded by Release 3, kept for reference.
---

The Token2 PIN+ Release 2 family was the first generation of Token2's PIN complexity enforcing FIDO2 keys. Per Token2's firmware feature support matrix, both Release 1 and Release 2 are now end of life. The current PIN+ keys ship on Release 3.x firmware. See [PIN+ Release 3](../token2-pin-plus-r3/) for the current line.

Existing Release 2 keys continue to function as FIDO2 authenticators. They cannot be upgraded to Release 3 firmware in the field.
