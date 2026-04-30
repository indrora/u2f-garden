---
title: "TrustKey B210H"
draft: false
vendor: trustkey
vendor_link: https://www.trustkeysolutions.com/
purchase:
  amazon:
  vendor: https://www.trustkeysolutions.com/
features:
  - u2f
  - fido
  - fido-l2
  - biometric
  - resident
  - resident-ecdsa
  - hotp
  - totp
  - windows-hello
  - management-app
  - management-app-win
  - management-app-mac
interfaces:
  - usba
summary: The B210 with Windows Hello support added. One fingerprint enrolment serves both FIDO and Windows logon.
---

The B210H extends the [B210](../trustkey-b210/) with Windows Hello support. The same physical fingerprint enrolment satisfies the FIDO2 user verification check and the Windows logon Hello check, which avoids forcing users to enrol fingerprints twice.

This is the natural pick for an enterprise that uses Windows Hello for Business and Microsoft Entra ID for federated identity, since one device covers desktop logon, application sign in, and FIDO2 second factor.
