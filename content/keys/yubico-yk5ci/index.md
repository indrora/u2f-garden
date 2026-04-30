---
title: "Yubikey 5Ci"
draft: false
vendor: yubico
vendor_link: https://www.yubico.com/products/yubikey-5-overview/
deprecated: false
purchase:
  amazon: B07MDDBT63
  vendor: https://www.yubico.com/product/yubikey-5ci/
features:
  - u2f
  - yubiotp
  - smartcard
  - stored-password
  - resident
  - resident-ecdsa
  - resident-ed25519
  - fido
  - fido-l2
  - ctap21
  - hotp
  - totp
  - management-app
  - management-app-win
  - management-app-mac
  - management-app-android
  - management-app-ios
interfaces:
  - usbc
  - lightning
summary: The Yubikey 5Ci pairs a USB-C connector with an Apple Lightning connector for users with older iPhones and iPads.
---

The Yubikey 5Ci is the only mass produced security key that pairs a USB-C connector with an Apple Lightning connector. For users on iPhone 14 or older, or older iPads with Lightning, this is the most direct way to use a hardware key on iOS without going through NFC.

Apple's move to USB-C on the iPhone 15 and later means the Lightning side of this key is increasingly legacy. Yubico still sells it, and a [FIPS variant](../yubico-yk5-fips/) is also produced, but no successor model has been announced. New iPhone owners will probably be better served by the [Yubikey 5C NFC](../yubico-yk5/), which uses NFC for tap to authenticate against current iPhones.

The 5Ci supports the full Yubikey 5 protocol stack: FIDO2, U2F, OATH HOTP and TOTP through the Yubico Authenticator app, PIV smart card, OpenPGP, YubiOTP, and static passwords.

## EUCLEAK

Like the rest of the Yubikey 5 family, the 5Ci is in scope of the EUCLEAK side channel disclosed in September 2024. Firmware 5.7 contains the fix and units shipping after May 2024 are not affected. See the [Yubikey 5](../yubico-yk5/) entry for the full background.
