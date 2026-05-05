---
title: Why use a security key?
draft: false
---

When you log into a website, you probably use a username and a password. That used to be enough. In 2026, it isn't. Phishing sites look identical to real ones, password databases leak constantly, and the techniques attackers use to steal credentials have moved well beyond email scams that misspell the company name.

A hardware security key is a small physical device, usually the size of a USB stick, that proves to a website you are physically in possession of the key. It does this with a cryptographic challenge that is bound to the website's actual domain. If you ever land on a phishing page, the key refuses to authenticate, because the domain is wrong. That single property is what makes hardware keys phishing resistant in a way that codes from a text message, an authenticator app, or a printed list never can be.

# What is multi factor authentication?

Multi factor authentication is the practice of requiring more than one piece of evidence to prove who you are. The factors are usually:

* Something you know, like a password.
* Something you have, like a hardware key or a phone with a secure enclave.
* Something you are, like a fingerprint or face scan.

The United States National Institute of Standards and Technology (NIST), which sets the security baselines used by federal agencies and many private sector regulators, [recommends moving away from the reliance on memorised passwords](https://pages.nist.gov/800-63-4/sp800-63b.html) and onto authenticator devices that resist phishing.

# Why this matters

Passwords leak constantly. Sites like [Have I Been Pwned](https://haveibeenpwned.com/) make it easy to check whether your email has shown up in a breach. The answer is usually yes. Once an attacker has a password from one breach, they will try the same password on every other site, and that is how most account takeovers happen.

* Access to your email account is access to every other account, because email is the channel for password resets.
* Access to your bank account or your investment broker can drain accounts in minutes.
* Access to your social accounts can be used to defraud your friends, your family, or your employer.

A second factor turns "the attacker has my password" from "I just lost everything" into "the attacker hit a wall." A hardware key in particular turns it into "the attacker hit a wall that does not get easier with more attempts."

# What about passkeys?

Passkeys are the marketing name for WebAuthn discoverable credentials. They are the same underlying technology as FIDO2 second factors, just used as the only authentication step rather than as a second step on top of a password. Passkeys synced through your phone's cloud account are convenient. Passkeys held on a hardware key are stronger, because they cannot be silently exfiltrated through a cloud account compromise.

Most current hardware keys can hold passkeys. Buying a key today gives you the option to use it as a second factor, as a passkey holder, or both, depending on the site and your preferences.

# Where to start

If you have never used a hardware key before, the easiest entry point is a [Yubico Security Key NFC](/keys/yubico-fido2/) or a [Google Titan Security Key](/keys/google-titan-key-gen3/). Both are inexpensive, both are widely supported, and both will work with every major identity provider. Buy two so you have a backup.

From there, browse the [full key catalog](/keys/) by feature, by interface, or by vendor.
