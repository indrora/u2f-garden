---
title: "Yubikey Bio Multi-protocol Edition"
draft: false
vendor: yubico
vendor_link: https://www.yubico.com/products/yubikey-bio-series/
deprecated: false
purchase:
  amazon:
  vendor: https://www.yubico.com/product/yubikey-bio-series/
features:
  - u2f
  - fido
  - fido-l2
  - ctap21
  - resident
  - resident-ecdsa
  - resident-ed25519
  - smartcard
  - biometric
  - windows-hello
  - management-app
  - management-app-win
  - management-app-mac
interfaces:
  - usba
  - usbc
summary: The Bio with PIV. Yubico's biometric key with a smart card stack on top. Sold through YubiKey as a Service only.
---

The Yubikey Bio Multi-protocol Edition is Yubico's answer to a long standing complaint about the original [Yubikey Bio FIDO Edition](../yubico-yk5bio/): users wanted biometrics and PIV smart card support on the same device. This model adds PIV on top of FIDO2 and the capacitive fingerprint sensor.

It does not bring back YubiOTP, OATH, OpenPGP, or static passwords. If you want everything, you still want a regular [Yubikey 5](../yubico-yk5/). If you want fingerprints with PIV for Windows logon and federated identity, this is the key.

The Multi-protocol Edition is sold only through Yubico's enterprise YubiKey as a Service or Compliance tier subscriptions, not through the public store. Both USB-A and USB-C variants exist.

## Fingerprint behaviour

The fingerprint sensor satisfies user verification for both FIDO2 and PIV operations. Up to five fingerprints can be enrolled per key. Failed fingerprints fall back to PIN.
