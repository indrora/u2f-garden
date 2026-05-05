---
title: Frequently Asked Questions
draft: false
---

Here are some questions people often ask.

# Why should I use a security key instead of SMS for my second factor?

SMS messages can be intercepted, redirected, and stolen. Attackers use [SIM swapping](https://en.wikipedia.org/wiki/SIM_swap_scam) to take control of a phone number, after which they can read texts, receive calls, and reset accounts. The mobile networks themselves also have well documented weaknesses in the SS7 signalling layer that can be used to intercept text messages without the user's carrier ever knowing.

A hardware security key sidesteps the entire telephone network. It uses a cryptographic challenge and response that is bound to the website's domain, so even if an attacker fools you into typing your password into a phishing page, the key will refuse to authenticate against the wrong domain.

For more background, see:

* [SIM swapping attacks and what the FCC is doing about them](https://krebsonsecurity.com/2021/10/fcc-proposal-targets-sim-swapping-port-out-fraud/)
* [Weaknesses in mobile telephone networks](https://www.wired.com/2017/05/fix-ss7-two-factor-authentication-bank-accounts/)

# What is a passkey, and how does it relate to my hardware key?

A passkey is a discoverable WebAuthn credential. It can live in a hardware key, in a phone, in a password manager, or in your operating system's secure storage. The marketing term "passkey" got popular in 2023 and 2024 because the major browsers and platforms agreed on syncing passkeys across devices through cloud accounts (iCloud Keychain, Google Password Manager, 1Password, and so on).

A hardware security key holds passkeys that do not sync. They live on the physical device. That is a feature, not a bug, for high assurance use cases: a stolen cloud account cannot exfiltrate the credential. The tradeoff is that if you lose the key, the passkeys it held are gone.

In short: every modern security key can be a passkey holder. Synced passkeys are convenient. Hardware backed passkeys are stronger.

# Do I need a different key for every site?

No. A modern FIDO2 key can be registered against effectively unlimited sites for non discoverable credentials, where the website remembers the credential and the key only stores a master secret. For discoverable credentials, where the key remembers the credential itself, capacity varies by model. Older keys hold around 25 credentials. Current generation keys hold from 100 to 300 depending on vendor.

# What happens if I lose my key? What about backups?

The standard advice is to register at least two keys against every account that supports more than one. Buy two keys at the same time. Register both during initial setup. Keep one on you, keep one somewhere safe. If you lose the daily key, your backup still works, and you can rotate without losing access.

Some services also issue [backup codes](https://support.google.com/accounts/answer/1187538), which are one time recovery codes you print and keep safe. These are useful but they are no substitute for a backup hardware key, since they often grant full account access without the phishing resistance the key provides.

For the technical reasons backup codes are still uncommon and why hardware keys cannot be cloned, see [our writeup on FIDO cloning](/posts/2022/05-05-fido-cloning/).

# Are hardware keys still safe after EUCLEAK?

Yes, with caveats. EUCLEAK is a side channel attack disclosed in September 2024 that affects keys built on the NXP A700x secure element family, including the Yubikey 5 series, Yubikey 5 FIPS series, Security Key Series, and Google Titan keys. The attack requires physical possession of the key, removal of its plastic shell, and around eleven thousand dollars worth of equipment. For most threat models that is well outside the realistic attacker.

Yubico fixed the issue in firmware 5.7. Pre 5.7 keys cannot be updated in the field. If your threat model includes nation state actors with physical access to your key, replace pre 5.7 units. If it does not, keep using your existing key.

For more background, see [the EUCLEAK explainer](/posts/2026/euclear-and-your-yubikey/) and [Yubico's advisory YSA-2024-03](https://www.yubico.com/support/security-advisories/ysa-2024-03/).

# Do hardware keys replace password managers?

No, but they pair well. A password manager handles every credential that does not yet support FIDO2, which is still the majority of accounts. A hardware key handles the high value accounts where you want phishing resistance: email, banking, identity providers, code signing, your password manager itself.

The right setup for most people is a password manager protected by a hardware key, with a second hardware key as backup, and important accounts inside the password manager all upgraded to passkeys or FIDO2 second factors where possible.

# What about FIPS validation? Do I need that?

Almost certainly not. FIPS 140-2 and 140-3 validation are required for United States federal agencies, contractors working with them, and certain regulated industries (some healthcare and financial configurations). For everyone else, the FIPS variant is the same hardware as the standard variant, with a higher price and a slower release cadence. Buy the standard model unless your employer or regulator specifically requires FIPS.

# Bluetooth keys?

The era of Bluetooth security keys is essentially over. Google's Bluetooth Titan was discontinued in 2021 after a pairing flaw. No major vendor has launched a new Bluetooth only key since. Bluetooth survives only as a secondary transport on a small number of multi mode keys.

If you see a Bluetooth security key on the market today, it is almost always a multi mode device where Bluetooth is one of several transports.
