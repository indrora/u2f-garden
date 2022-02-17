---
title: "Yubikey 5"
draft: false
vendor: Yubico
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
  - fido-l1
  - management-app
  - management-app-win
  - management-app-mac
  - management-app-android
interfaces:
  - usba
  - usbc
  - nfc
summary: Yubico's flagship product, the Yubikey 5 is one of the most feature complete security tokens on the market. 
---

Yubikeys are credited with starting the personal USB token industry, and for good measure. With the fifth generation of yubikey comes a unification of the overall line. The 5ci and Nano lack NFC, but the classic Yubikey series has NFC as a standard feature. 

In addition to U2F functions, the YubiKey supports PKCS#11 PIV (Smart Card) functionality. For more information, see [Yubikey as a PIV Compatible Smart Card](https://www.yubico.com/authentication-standards/smart-card/) on the Yubico website.

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