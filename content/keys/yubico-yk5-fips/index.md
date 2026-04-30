---
title: "Yubikey 5 FIPS Series"
draft: false
vendor: yubico
vendor_link: https://www.yubico.com/products/yubikey-fips/
deprecated: false
purchase:
  amazon:
  vendor: https://www.yubico.com/product/yubikey-5-fips-series/
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
  - fips140-2
  - hotp
  - totp
  - management-app
  - management-app-win
  - management-app-mac
  - management-app-android
interfaces:
  - usba
  - usbc
  - nfc
  - lightning
summary: The Yubikey 5 family in a FIPS validated configuration. For United States federal agencies and regulated industries.
---

The Yubikey 5 FIPS Series is the same hardware as the standard Yubikey 5 family, configured and validated for FIPS 140-2. It is sold as 5 NFC FIPS, 5C NFC FIPS, 5C FIPS, 5 Nano FIPS, 5C Nano FIPS, and 5Ci FIPS, matching the standard lineup variant for variant.

The FIPS validation under 140-2 carries through May 2026. Yubico has submitted the series for [FIPS 140-3 Level 2 validation with Physical Level 3](https://www.yubico.com/blog/yubico-submits-yubikey-5-fips-series-for-fips-140-3-validation/), expected to clear in the second quarter of 2026.

## When you actually need this

You need FIPS validation if you are a United States federal agency, a contractor working with one, a healthcare organisation under specific HIPAA configurations, or a financial services firm operating under one of the regulators that has adopted FIPS as a requirement. Most other users do not benefit from the FIPS series and should buy the standard line.

The FIPS series currently runs on firmware 5.4, which means a noticeably smaller discoverable credential capacity than the 5.7 firmware on the standard line. The 5 FIPS series stores around 25 passkeys per key, where the current 5 series stores around 100. If you are operating in a passkey heavy environment, this matters.

## EUCLEAK

The 5 FIPS series is in scope for EUCLEAK. Firmware 5.7 contains the fix. See the [Yubikey 5](../yubico-yk5/) entry for the wider context. Yubico has guidance for FIPS customers about replacement for the affected production runs.
