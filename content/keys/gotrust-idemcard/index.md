---
title: IdemCard
draft: false
vendor: gotrust
vendor_link: https://www.gotrustid.com/idem-card
purchase:
  amazon: B07YS68Y47
  vendor: null
features:
  - u2f
  - smartcard
  - fido
  - fido-l1
interfaces:
  - bluetooth
  - nfc
  - smartcard
summary: For those willing to do the legwork, a holdable option for wireless authentication.
lede: NFC, Bluetooth, and SmartCard together? Ditching the traditional USB connector, this option gives a low cost option to try something different.
---

GoTrust's IdemCard is a unique offering. For those who need SmartCard access, this can definitely be an option. 

Paired with their IdemKey, the IdemCard makes a great one-two punch solution for securing accounts.
The hitch here is that you'll need to either have a laptop with bluetooth or be able to set up the card with a phone.
This means that if you're using Google's 2FA, you'll need to do some legwork.
HowToGeek has a [comprehensive tutorial](https://www.howtogeek.com/365045/how-to-set-up-and-use-the-google-titan-key-bundle/) on setting up Bluetooth tokens using a phone.

Under Windows, it appears that the Windows Hello FIDO2 interface will recognize this via the SmartCard interface, if you have a reader. Under certain circumstances, Windows may require you to remove and re-insert the card to make sure that you're human. 
This behavior has been confirmed to work with Microsoft Edge as of Februrary 2022.

Windows does require a short amount of setup to register the card with Windows Hello
Preliminary evidence also says that this *potentially* disables or changes NFC compatibility. 
This was reported to [@indrora](https://github.com/indrora/) by a friend. 



# Battery life

Claimed: About 2 months. Included in the box is a USB charger. A standard SmartCard reader will, also, charge it. 

# Other interfaces not listed

TrustID claims this will work with "everything except FeLiCa" which is a bold claim to make. 
