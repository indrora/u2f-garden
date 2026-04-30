---
title: "EUCLEAK and your Yubikey"
date: 2026-04-30
publishdate: 2026-04-30
lastmod: 2026-04-30
draft: false
tags: ["Editorial", "Yubico", "Security"]
author: waffles
---

In September 2024, security researchers at NinjaLab disclosed [EUCLEAK](https://ninjalab.io/wp-content/uploads/2024/09/20240903_eucleak.pdf), a side channel attack against the Infineon ECDSA library running on the NXP A700x family of secure elements. That family of chips ships inside Yubico's Yubikey 5 series, the Yubikey 5 FIPS series, the Security Key Series, and the Google Titan keys. Roughly speaking, every popular FIDO2 token built on that platform is in scope.

If you own a Yubikey, you probably saw the headlines and wondered if you needed to throw your key in the trash. The short answer is no. The longer answer is more interesting, and it is worth understanding so you can make a sensible decision about whether to replace your key.

# What the attack actually does

EUCLEAK is a side channel attack. The attacker measures electromagnetic emissions from the secure element while the chip performs ECDSA signing operations. With enough captured signatures and enough careful analysis, the attacker can reconstruct the private key.

The catch is what is required to do this in practice:

* Physical possession of the key.
* Removal of the plastic shell. This destroys the key, so you cannot do this and put the key back without the owner noticing.
* Around eleven thousand United States dollars worth of equipment, primarily an oscilloscope and an electromagnetic probe.
* Hours of careful work, including capturing thousands of signatures, which means the attacker also needs to know the PIN if one is set.
* Specialised expertise in side channel cryptanalysis.

Compare this to a phishing attack. Phishing requires zero physical access, costs effectively nothing, and is automated at scale. The realistic threat model for ninety nine point nine percent of users is a phishing attack, and a Yubikey shuts that down completely. EUCLEAK is a real attack and a meaningful disclosure, but it is in a fundamentally different category.

# What Yubico did

Yubico responded with [advisory YSA-2024-03](https://www.yubico.com/support/security-advisories/ysa-2024-03/) and [firmware 5.7](https://docs.yubico.com/hardware/yubikey/yk-tech-manual/5.7-firmware-specifics.html), which replaces Infineon's ECDSA library with one written by Yubico that does not have the same side channel weakness. Firmware 5.7 also brings unrelated improvements, including CTAP 2.1, Ed25519 support, RSA-3072 and RSA-4096, enterprise attestation, enhanced PIN complexity, and restricted NFC mode.

Crucially, Yubikey firmware cannot be updated in the field. There is no patch path for an existing key. If you bought a Yubikey before May 2024, your key is on a firmware that is still vulnerable to EUCLEAK. The only mitigation is replacement.

Yubico has been honest about this. They publish [a tool to check your firmware version](https://www.yubico.com/products/yubikey-5-overview/) through the Yubico Authenticator app. If you see anything below 5.7, your key is in scope of the vulnerability.

# Should you replace your key?

It depends on your threat model. Ask yourself:

* Could a sufficiently motivated and well funded attacker get physical access to your key for several hours, without you noticing?
* Is the data your key protects worth the eleven thousand dollar plus skilled labour cost to that attacker?

If the answer to either is no, your existing pre 5.7 key is still doing its job. The phishing resistance that made you buy the key in the first place is unaffected.

If the answer to both is yes, you are in a small group: senior officials, intelligence targets, journalists in hostile environments, custodians of significant cryptocurrency keys, and similar. Replace your key with a 5.7 firmware unit. Yubico has a [trade in program](https://www.yubico.com/) for some affected customers.

# What this means for the broader market

EUCLEAK is not unique to Yubico. The same NXP A700x family ships in Google Titan keys and a handful of other vendors that license the same secure element. Google has not issued a recall and the practical risk profile is the same as for Yubico: physical access required, expensive lab equipment required, currently shipped Titans use updated cryptography.

For other vendors, ask the same questions you would ask after any disclosure. What chip is this key built on? Has the vendor responded? Is there a firmware fix? If yes, can you update? If no, what is the replacement path?

This is one of the reasons the catalog now distinguishes CTAP 2.1 from CTAP 2.0 and notes hardware boundaries explicitly. The boring details matter when something like EUCLEAK lands.

# In short

* EUCLEAK is real. It affects the NXP A700x family used by Yubikey 5, Yubikey 5 FIPS, Security Key Series, and Google Titan.
* The attack requires physical possession, key destruction, and around eleven thousand dollars of lab equipment.
* Yubico fixed it in firmware 5.7. Pre 5.7 keys cannot be updated.
* For most users, this does not warrant replacement. For high assurance users, it does.
* The attack does not weaken the phishing resistance that is the actual reason you bought the key.

If you are unsure, the conservative answer is to register a 5.7 or later key as a backup against your important accounts and keep your existing key in service. If something goes wrong with the older key, you still have access. If nothing goes wrong, you have a second key, which is what every guide tells you to have anyway.
