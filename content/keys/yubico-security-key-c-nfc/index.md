---
title: "Yubico Security Key C NFC"
draft: false
vendor: yubico
vendor_link: https://www.yubico.com/products/security-key/
deprecated: false
purchase:
  amazon: B0B4N3CFZ4
  vendor: https://www.yubico.com/product/security-key-c-nfc-by-yubico/
features:
  - u2f
  - fido
  - fido-l2
  - ctap21
  - resident
  - resident-ed25519
  - resident-ecdsa
interfaces:
  - usbc
  - nfc
summary: USB-C sibling to the Security Key NFC. Same FIDO only feature set, twenty nine United States dollars.
---

The Yubico Security Key C NFC is the USB-C version of the [Security Key NFC](../yubico-fido2/). Both are FIDO only, dropping the YubiOTP, PIV, OATH, and OpenPGP slots that the Yubikey 5 carries. Both store discoverable credentials so they work as passkey holders.

If you have a modern laptop or phone with USB-C, this is the right pick. The USB-A model is still useful for desktops with older ports.

## EUCLEAK

The Security Key C NFC sits on the same NXP A700x secure element as the rest of the family. Keys with firmware 5.7 or newer contain the EUCLEAK fix. See the [Yubikey 5](../yubico-yk5/) entry for context.
