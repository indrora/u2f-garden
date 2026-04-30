---
title: "Yubico Security Key NFC"
draft: false
vendor: yubico
vendor_link: https://www.yubico.com/products/security-key/
purchase:
  amazon: B07M8YBWQZ
  vendor: https://www.yubico.com/product/security-key-nfc-by-yubico/
features:
  - u2f
  - fido
  - fido-l2
  - ctap21
  - resident
  - resident-ed25519
  - resident-ecdsa
interfaces:
  - usba
  - nfc
summary: A cut-down Yubikey, the Security Key Series provides a classic form with wide function at a lower price.
---

The Yubico Security Key NFC is the FIDO only sibling of the [Yubikey 5](../yubico-yk5/). It drops PIV smart card, OpenPGP, OATH, YubiOTP, and the static password slots, and keeps the parts most people actually use: FIDO2 and WebAuthn, including discoverable credentials for passkeys.

It comes in a USB-A plus NFC variant and a USB-C plus NFC variant. The USB-C model has its own page at [Yubico Security Key C NFC](../yubico-security-key-c-nfc/). Yubico also sells a [Security Key Enterprise Edition](../yubico-security-key-enterprise/) of both keys, which adds enterprise attestation for organisations that want serial numbers tied to registrations.

## U2F SSH

The Security Key supports Ed25519 and ECDSA stored keys. Generating them and using them is identical to the Yubikey 5.

## EUCLEAK

The Security Key Series is built on the same NXP A700x secure element as the Yubikey 5 and is therefore in scope of the [EUCLEAK side channel](https://www.yubico.com/support/security-advisories/ysa-2024-03/) disclosed in September 2024. Keys with firmware 5.7 or later contain the fix. Older keys cannot be updated and remain vulnerable to a well funded attacker with physical access. For most threat models the key is still safe to use, but if your threat model includes nation state actors who can take your key for an afternoon, replace pre 5.7 units.
