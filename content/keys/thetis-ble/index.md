---
title: "Thetis BLE FIDO2"
draft: false
vendor: thetis
vendor_link: https://thetis.io/products/fido2-ble-nfc-key
purchase:
  amazon:
  vendor: https://thetis.io/products/fido2-ble-nfc-key
features:
  - u2f
  - fido
  - resident
  - hotp
  - totp
interfaces:
  - usba
  - nfc
  - bluetooth
summary: One of the few current FIDO2 keys with Bluetooth Low Energy as a transport.
---

The Thetis BLE FIDO2 is one of a small number of currently sold FIDO2 keys that include Bluetooth Low Energy as a transport, alongside USB-A and NFC. Most BLE only keys were retired after the Google Bluetooth Titan was discontinued in 2021. Thetis kept BLE in their line as a secondary transport rather than a primary one.

Bluetooth pairing for FIDO authentication is uncommon in consumer flows and most relying parties prefer NFC or USB. The presence of BLE here is mainly useful in a phone paired enterprise scenario, or for users who specifically need wireless authentication and cannot use NFC.
