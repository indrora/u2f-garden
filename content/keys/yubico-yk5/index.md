---
title: "Yubikey 5"
draft: false
vendor: yubico
vendor_link: https://www.yubico.com/products/yubikey-5-overview/
purchase:
  amazon: B07HBD71HL
  vendor: https://www.yubico.com/store/#for-professionals
features:
  - u2f
  - yubiotp
  - smartcard
  - stored-password
  - resident-ecdsa
  - resident-ed25519
  - resident
  - fido
  - fido-l2
  - ctap21
  - hotp
  - totp
  - enterprise-attestation
  - management-app
  - management-app-win
  - management-app-mac
  - management-app-android
  - management-app-ios
interfaces:
  - usba
  - usbc
  - nfc
summary: Yubico's flagship product, the Yubikey 5 is one of the most feature complete security tokens on the market. 
---

Yubikeys are credited with starting the personal USB token industry, and for good measure. With the fifth generation of Yubikey comes a unification of the overall line. The 5Ci and Nano variants lack NFC, but the rest of the family carries NFC as a standard feature.

The Yubikey 5 family ships in many variants. This entry covers the standard line: Yubikey 5 NFC, 5C NFC, 5C, 5 Nano, and 5C Nano. The variants with meaningfully different feature sets have their own pages:

* [Yubikey 5Ci](../yubico-yk5ci/) for users with older iPhones that still use a Lightning connector.
* The [Yubikey 5 FIPS](../yubico-yk5-fips/) family for FIPS 140 compliance.

The Yubikey Bio family is documented separately as well: see [Yubikey Bio FIDO Edition](../yubico-yk5bio/) and [Yubikey Bio Multi-protocol Edition](../yubico-yk5-bio-multi/). For a FIDO only sibling at a lower price, see the [Security Key NFC](../yubico-fido2/).

In addition to FIDO2 and U2F, the Yubikey 5 supports PKCS#11 PIV (smart card) functionality. For more information, see [Yubikey as a PIV Compatible Smart Card](https://www.yubico.com/authentication-standards/smart-card/) on the Yubico website.

## Firmware 5.7 and EUCLEAK

In September 2024, security researchers at NinjaLab disclosed [EUCLEAK](https://ninjalab.io/wp-content/uploads/2024/09/20240903_eucleak.pdf), a side channel attack against the Infineon ECDSA library running on the NXP A700x secure element used by the Yubikey 5 series, the Yubikey 5 FIPS series, the Security Key Series, and the Google Titan keys. The attack requires physical possession of the key, removal of its plastic shell, and around eleven thousand dollars worth of equipment, so the practical risk to most users is low. Yubico's [advisory YSA-2024-03](https://www.yubico.com/support/security-advisories/ysa-2024-03/) has the full details.

Yubico fixed the issue in firmware 5.7, released in May 2024, by replacing Infineon's library with a Yubico written implementation. Firmware on Yubikeys cannot be updated in the field, so a Yubikey 5 you bought before May 2024 is still affected. The mitigation in that case is replacement, not patching.

Firmware 5.7 also brings CTAP 2.1, RSA-3072 and RSA-4096, Ed25519, enterprise attestation, enhanced PIN complexity, restricted NFC mode, and a higher discoverable credential capacity. If you are buying a new Yubikey 5 today, it will be on 5.7 or higher.

## Using the Yubikey with other services

The Yubikey series supports OpenPGP keys as well as other cryptographic functions through the SmartCard interface.

Several community guides exist on these topics:

* [Configuring OpenPGP and Yubikeys](https://zach.codes/ultimate-yubikey-setup-guide/) (the "Ultimate Yubikey Setup Guide")
* [Yubikey GPG and SSH Auth on Windows and WSL](https://blog.oxycode.one/yubikey-gpg-and-ssh-auth-on-windows-and-wsl)


### TOTP/HOTP and the Yubikey series

Yubikeys support TOTP and HOTP through the [Yubico Authenticator](https://www.yubico.com/products/yubico-authenticator/) application. This application allows adding and removing TOTP and HOTP credentials.
These are stored on the key, not on the phone or desktop, however it is not possible to retrieve the secret once
the values have been added.

### ED25519 support in SSH U2F

Support for ED25519 is limited to firmware 5.2.3 and above (supporting FIDO2). ([source](https://cryptsus.com/blog/how-to-configure-openssh-with-yubikey-security-keys-u2f-otp-authentication-ed25519-sk-ecdsa-sk-on-ubuntu-18.04.html)) This may be important to you if you have [concerns over ECDSA](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm#Concerns). 