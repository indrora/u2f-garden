---
title: TrustKey T110
draft: false
vendor: trustkey
vendor_link: https://www.trustkeysolutions.com/security-keys/t110/
purchase:
  amazon: B086QTS5YM
  vendor: https://www.trustkeysolutions.com/store/products/t110/
features:
  - u2f
  - totp
  - hotp
  - fido 
  - fido-l1
  - resident
  - ssh-ecdsa
  - management-app
  - management-app-win
  - management-app-mac
interfaces:
  - usba
summary: TrustKey's entry level token provides a large number of options for authentication but requires software for non-U2F features.
lead: The TrustKey T110 provides a plethora of options for authenticaiton, including HOTP and TOTP, resident SSH keys, and more, but is hampered by a convoluted management application.
---

From its feature list, the TrustKey T110 would look like a perfect replaceement for Yubico's Yubikey. On the surface, that's correct, but features alone are deceiving. 

# HOTP and TOTP

Accessing HOTP and TOTP values is done through an application, the TrustKey Key manager, that runs on either MacOS or Windows. This application has three main functions:

* Adding/removing up to 50 TOTP/HOTP applications from the token
* Putting the generated TOTP/HOTP values in applications
* Setting the PIN and factory resetting the token

# SSH

The TrustKey T110 does support SSH Resident keys, but requires a PIN to be set *before* the SSH key is added. Failure to do so will result in the key saying it accepted the resident key, but silently dropping it. 