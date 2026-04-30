---
title: "Token2 PIN+ Release 3"
draft: false
vendor: token2
vendor_link: https://www.token2.com/shop/category/pin-plus-series
purchase:
  amazon:
  vendor: https://www.token2.com/shop/category/pin-plus-series
features:
  - u2f
  - fido
  - fido-l2
  - ctap21
  - resident
  - resident-ecdsa
  - resident-ed25519
  - smartcard
  - hotp
  - totp
  - enterprise-attestation
interfaces:
  - usba
  - usbc
  - nfc
summary: PIN+ with PIV smart card and OpenPGP on top. Release 3.3 is the current top end Token2 key.
---

Token2's PIN+ Release 3 is the current generation of the PIN+ line, replacing the now legacy [Release 2](../token2-pin-plus-r2/). It keeps the FIDO2 stack and on device PIN complexity enforcement, raises discoverable credential capacity to around 300 per key, and adds PIV smart card support. The Release 3.3 firmware further adds OpenPGP smart card support, putting the key in the same protocol space as a Yubikey 5 at a noticeably lower price.

Token2 ships PIN+ Release 3 in many form factors:

* USB-A and USB-A nonbranded variants on Release 3.3.
* USB-C on Release 3.3.
* Mini-A on Release 3.2 and Mini-C on Release 3.1, low profile USB nub variants.
* Dual port (USB-A plus USB-C in one body, no NFC) on Release 3.3.
* Dual Octo, the enterprise unbranded attestation variant on Release 3.3.
* NFC Card, a credit card form factor with NFC, on Release 3.3.
* PIN+Bio3, a fingerprint variant. See [PIN+Bio3](../token2-pin-plus-bio3/).

Release 3.4 is in development and adds NFC support to PIV operations through Secure Messaging. Release 3.5 and 3.6 are expected to add CTAP 2.3.

For the firmware feature differences across releases, Token2 maintains a [public matrix](https://www.token2.com/site/page/pin-firmware-feature-support-matrix-openpgp-fido2-otp-and-piv-across-releases).
