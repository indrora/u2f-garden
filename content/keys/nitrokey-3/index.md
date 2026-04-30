---
title: "Nitrokey 3"
draft: false
vendor: nitrokey
vendor_link: https://www.nitrokey.com/products/nitrokeys
purchase:
  amazon:
  vendor: https://shop.nitrokey.com/shop/nk3an-nitrokey-3a-nfc-147
features:
  - u2f
  - fido
  - fido-l1
  - ctap21
  - resident
  - resident-ecdsa
  - resident-ed25519
  - smartcard
  - hotp
  - totp
interfaces:
  - usba
  - usbc
  - nfc
summary: Nitrokey's open source flagship. FIDO2 with NFC plus a full OpenPGP and PIV smart card stack.
---

The Nitrokey 3 is the current generation Nitrokey, available in three form factors: the 3A NFC with USB-A and NFC, the 3C NFC with USB-C and NFC, and the 3A Mini, a smaller USB-A only nano variant. All three share the same firmware base, which is built on the open source Trussed framework.

The Nitrokey 3 supports FIDO2, U2F, OpenPGP smart card, PIV, OATH HOTP and TOTP, and a broader set of curves than most keys, including secp256k1 for cryptocurrency users. The discoverable credential capacity was raised to one hundred in early 2026 firmware.

Nitrokey publishes the firmware source and supports updating in the field, both unusual in this market. The hardware uses an EAL6+ certified secure element for key storage.

Older Nitrokey FIDO2 and Nitrokey FIDO U2F products are deprecated and have been superseded by the [Nitrokey Passkey](../nitrokey-passkey/) for FIDO only use cases and the Nitrokey 3 for everything else.
