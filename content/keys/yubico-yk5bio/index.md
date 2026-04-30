---
title: "Yubikey Bio FIDO Edition"
draft: false
vendor: yubico
vendor_link: https://www.yubico.com/products/yubikey-bio-series/
purchase:
  amazon:
  vendor: https://www.yubico.com/product/yubikey-bio-series/
features:
  - u2f
  - resident-ecdsa
  - resident-ed25519
  - resident
  - fido
  - fido-l2
  - ctap21
  - biometric
  - windows-hello
  - management-app
  - management-app-win
  - management-app-mac
  - management-app-android
interfaces:
  - usba
  - usbc
summary: Yubico's fingerprint security key, FIDO only. No NFC.
---

The Yubikey Bio FIDO Edition is Yubico's fingerprint capacitive sensor token. It supports only FIDO2 and U2F, with no NFC, no YubiOTP, no PIV, no OpenPGP, and no static password slots. Fingerprint enrolment and management is handled through the Yubico Authenticator application.

If you need biometrics with the rest of the Yubikey 5 protocol stack, see the newer [Yubikey Bio Multi-protocol Edition](../yubico-yk5-bio-multi/), which adds PIV smart card on top of FIDO2 and biometrics.

## Fingerprint behaviour

The on key fingerprint sensor unlocks the device for FIDO2 user verification. If the sensor fails three times in a row, you can fall back to the device PIN. Up to five fingerprints can be enrolled per key.

## EUCLEAK

The Bio FIDO Edition uses the same NXP A700x secure element family as the Yubikey 5, and so was originally in scope for the EUCLEAK disclosure. Yubikeys shipping on firmware 5.7 or higher contain the fix. See the [Yubikey 5 entry](../yubico-yk5/) for the full background.
