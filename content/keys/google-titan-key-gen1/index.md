---
title: "Titan Key (Gen1)"
draft: false
vendor: google
vendor_link: https://cloud.google.com/titan-security-key/
deprecated: true
purchase:
  amazon: null
  vendor: null
features:
  - u2f
  - fido
interfaces:
  - usba
  - bluetooth
  - nfc
Summary: No longer supported, but comprehensive solution to account security. 
---

Google's first generation Titan Keys were introduced under their Advanced Protection program. 
The pair of keys, a Bluetooth/USB and USB A + NFC set, were sold for $50. 


The keys are safe, however they are not recommended for new installations. Google has not issued
further Bluetooth U2F tokens in their later generations, saying in an [announcement](https://security.googleblog.com/2021/08/simplifying-titan-security-key-options.html):

{{< blockquote >}} 
Since NFC functionality is now supported by a wide range of Android phones and iPhones, we are discontinuing the Bluetooth Titan Security Key and focusing on the easier and more widely available NFC capability. However, for existing users with our Bluetooth Titan Security Keys, these will continue to work with Bluetooth and will continue to work as an NFC key on most modern mobile devices. Applicable warranties for existing Bluetooth Titan Security Keys will continue to be honored per their terms. All Titan Security Keys are built with a hardware secure element chip that includes firmware engineered by Google to verify the key’s integrity.
{{< /blockquote >}}

These keys were found to have a vulnerability in the Bluetooth dongle: According to a
[Google Security Blog post](https://security.googleblog.com/2019/05/titan-keys-update.html), the
Bluetooth tokens are vulnerable to an attack which requires proximity (about 30 feet) and
prior knowledge of some parts of the user's credentials already, on top of having a very small
time window.