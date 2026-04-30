---
title: "Yubico Security Key Enterprise Edition"
draft: false
vendor: yubico
vendor_link: https://www.yubico.com/products/security-key/
deprecated: false
purchase:
  amazon:
  vendor: https://www.yubico.com/products/yubikey-as-a-service/
features:
  - u2f
  - fido
  - fido-l2
  - ctap21
  - enterprise-attestation
  - resident
  - resident-ed25519
  - resident-ecdsa
interfaces:
  - usba
  - usbc
  - nfc
summary: The Security Key with a serial number you can read at registration. For organisations that want attestation tied to procurement.
---

The Security Key Enterprise Edition is structurally identical to the [Security Key NFC](../yubico-fido2/) and the [Security Key C NFC](../yubico-security-key-c-nfc/), but it ships with an Enterprise Attestation certificate. When an organisation has the right relying party configuration, the key reveals its serial number during FIDO registration. That lets identity teams tie a registered credential to a specific physical key, which in turn lets them invalidate registrations when a key is lost without affecting other users.

Yubico sells the Enterprise Edition through their YubiKey as a Service program rather than the public store. It is available in USB-A plus NFC and USB-C plus NFC.

This feature only matters if your identity provider actually consumes attestation. Microsoft Entra ID does, Google Workspace does, Okta does. Most consumer relying parties do not, so for personal use the regular Security Key NFC is the same key without the cost premium.
