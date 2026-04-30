---
title: "Octatco EzQuant"
draft: false
vendor: octatco
vendor_link: https://octatco.com/eng_product5
purchase:
  amazon:
  vendor: https://octatco.com/eng_product5
features:
  - u2f
  - fido
  - resident
  - resident-ecdsa
  - biometric
  - windows-hello
interfaces:
  - usba
  - nfc
summary: A fingerprint FIDO2 key with a quantum random number generator, co developed with SK Telecom and ID Quantique.
---

The EzQuant is Octatco's marquee product. It pairs the fingerprint FIDO2 stack from the [EzFinger2](../octatco-ezfinger2/) with an ID Quantique quantum random number generator embedded in the device. SK Telecom co developed the QRNG component.

In practical terms, the QRNG provides higher quality entropy for FIDO key generation than a typical pseudo random source. The functional FIDO behaviour is the same as any other FIDO2 key, so users do not need to do anything different to take advantage of it. Whether quantum sourced entropy is a meaningful upgrade for FIDO use cases is a debated topic, but the EzQuant is the only FIDO key shipping with one.
