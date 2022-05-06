---
title: Why cloning FIDO tokens is a bad idea
date: 2022-05-05
publishdate: 2022-05-08
lastmod: 2022-05-05
draft: true
tags: ["Editorial"]
author: indrora
---

I regularly see tech folks ask if it's possible to clone Yubikeys either for malicious or backup purposes. 

As an example of a comment I read on a popular news aggregator's comment section: 

> Are there any FIDO security keys that explicitly support backing up and restoring their master secrets? I would love to move from Username + Password + TOTP but my current workflow requires that I am able to regain access to my digital accounts using nothing but a few page paper backup including core service passwords & exported TOTP secrets.

# FIDO, safety, and certifications

Let's start by looking at how FIDO certifies tokens by level. By design, FIDO certification has only a few truly prescriptive rules. The FIDO Alliance outlines [their certification requirements](https://fidoalliance.org/certification/authenticator-certification-levels/) clearly:

* Level 1 is simply spec conformance with the structure of the FIDO protocol.
* Level 1+ requires the application or hardware to use easily auditable cryptography (e.g. Bouncycastle, libsodium, etc.)
* Level 2 requires hardware trusted execution enviornments (TEE) that has some defense against secret exfiltration. 
* Level 3 involves antitamper enclosures, protected memory, running in a TEE and validating itself. 
* Level 3+ involves everything below running on a certified secure platform

The highest level, L3+, is intended to push the boundaries and provide resistance against a stolen token being inspected under lab conditions. Roughly, anything above L1+ should have some sort of anti-exfiltration protection, and the FIDO alliance explicitly states that browsers, applications on a phone, or simply home-built hardware that does not consider "theft of the key" in its threat model as being important. 

This means that there's no *technical* limitation on such a thing as our wild commenter. 

# Failsafes and escape hatches

If one thing could be added to the U2F spec, I would require *Backup Codes* to be it. Currently, there are no standards for them, and each group does them differently. 

A common example of these is Google's 4-4 numeric codes. During setup, you're encouraged to download and print these, putting them into a safe place in case you're unable to log into your account using 2FA options otherwise. Likewise, GitHub presents 6-6 hexadecimal backup codes that you can use in case something goes awry with your existing 2FA options. 

Personally, I would like to see a means for the browser to use one of these codes as a backup authentication mechanism -- without the need for the site to generate them, shifting the generation and maintenance of them from the relying party (a fancy name for "the site you're authenticating to") and onto the authenticator itself. How this would be implemented I'm not certain. 

# The abilty to clone is a dangerous foot-gun

