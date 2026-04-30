---
title: "Google Titan Security Key"
draft: false
vendor: google
vendor_link: https://store.google.com/product/titan_security_key
deprecated: false
purchase:
  amazon: null
  vendor: https://store.google.com/product/titan_security_key
features:
  - u2f
  - fido
  - fido-l1
  - resident
  - resident-ecdsa
interfaces:
  - usba
  - usbc
  - nfc
summary: Google's current Titan keys, sold at thirty United States dollars in two variants, are FIDO2 capable and store passkeys on device.
---

The current Google Titan Security Keys come in two form factors at thirty United States dollars each. A USB-C model with NFC, and a USB-A model with NFC that ships with a USB-C to USB-A adapter. Both are FIDO2 and U2F capable, store discoverable credentials for passkeys, and are sold directly through the [Google Store](https://store.google.com/product/titan_security_key). They are produced by Feitian, similar to the [Feitian ePASS NFC](../feitian-epass-nfc/) but with a Google specific firmware build.

The original Titan launch in 2018 included a Bluetooth Low Energy version. After a pairing flaw was disclosed in 2019, Google [stopped selling the BLE Titan in 2021](https://security.googleblog.com/2021/08/simplifying-titan-security-key-options.html). See the [Titan Gen 1](../google-titan-key-gen1/) entry for that history. There is no current Bluetooth Titan and there is no announced successor.

## Passkey support

Since 2023, Titan keys store discoverable credentials, so they can act as a passkey holder rather than just a second factor. Google advertises capacity of around 250 passkeys per key. Resident credentials require a PIN, which the user sets on first registration.

## EUCLEAK and the NXP A700x family

The Titan keys are built on the same NXP A700x secure element family that is in scope for the [EUCLEAK disclosure](https://ninjalab.io/wp-content/uploads/2024/09/20240903_eucleak.pdf) from September 2024. The attack requires physical possession, shell removal, and specialist equipment. Google has not issued a recall, since the practical risk is low, but high assurance users with older Titan keys may want to rotate to current production runs.
