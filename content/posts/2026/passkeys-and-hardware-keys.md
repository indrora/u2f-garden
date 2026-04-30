---
title: "Passkeys and hardware keys, what is the difference?"
date: 2026-04-30
publishdate: 2026-04-30
lastmod: 2026-04-30
draft: false
tags: ["Editorial", "Passkey"]
author: waffles
---

The word "passkey" started showing up in marketing material in 2023. By 2026 it is everywhere. Apple, Google, and Microsoft all market passkey support. Banks now offer passkeys. Password managers all sync them. Browsers prompt you to create a passkey on every login.

If you have been using hardware security keys for years, the marketing is confusing, because it talks about passkeys as if they are something new. They are not. Passkeys are a marketing name for a technology that has shipped in your hardware key since FIDO2 launched.

This is a short explanation of what is actually going on, and what it means if you already own a hardware key or are thinking about buying one.

# The technology behind a passkey

A passkey is a WebAuthn discoverable credential. WebAuthn is the web standard that lets a website ask your authenticator (a hardware key, a phone, an operating system) to prove you control a particular cryptographic key.

There are two ways a website can store the credential.

* The website can store an encrypted version of the credential and hand it back to your authenticator at login time. The authenticator decrypts and signs. This is a non discoverable credential. The website remembers the credential, the authenticator does not.
* The authenticator can store the credential itself, indexed by the website. At login time, the website asks the authenticator "do you have a credential for me?" and the authenticator responds with the user's credential. This is a discoverable credential.

A discoverable credential is what current marketing calls a passkey. Same bytes, same protocol. The marketing wraps it in a friendlier word and ties it to user experiences like phone to phone sync.

# Where the credential lives matters

The protocol does not care where the discoverable credential is stored, only that the authenticator has it and can produce a signature when asked. In practice there are three common storage locations.

**On a hardware key.** The credential is bound to that physical device. If you lose the device, the credential is gone. There is no sync. This is what every FIDO2 hardware key has been doing since FIDO2 launched. The Yubikey 5, Security Key NFC, Nitrokey 3, Token2 PIN+, Feitian ePass, and every other modern key does this.

**In a phone or laptop's secure storage.** Apple stores passkeys in iCloud Keychain. Google stores them in Google Password Manager. Microsoft stores them in Windows Hello. These are synced to the cloud, end to end encrypted, and replicate across your devices logged into the same cloud account.

**In a password manager.** 1Password, Bitwarden, Dashlane, and others now store passkeys, also synced through their own infrastructure.

The user experience is mostly the same. The security properties are not.

# What changes when the passkey is synced

Synced passkeys are convenient. Lose your phone, get a new phone, log into your cloud account, your passkeys come with you. This solves the biggest practical problem with FIDO2: losing the authenticator used to mean losing access to every account where you registered it.

The cost is that synced passkeys live wherever your cloud account lives. If your iCloud is compromised, the attacker has your iCloud passkeys. The encryption is end to end, so an attacker would also need to compromise a device that has the keychain unlocked, but the threat surface is meaningfully larger than a key sitting in your pocket.

Synced passkeys also fail open in some browser flows when the user is on a device that does not have the credential. The browser will offer to use a phone as the authenticator over a Bluetooth proximity flow (the FIDO Alliance calls this hybrid transport, sometimes labelled caBLE). This is a feature for usability and a tradeoff for security. A nation state attacker who has compromised the relying party can social engineer this flow to get the user to authenticate from an unfamiliar device.

Hardware key passkeys do not sync. The credential is on the key. If you want it on two keys, you register both, the same way you have always done. The credential cannot be silently exfiltrated through a cloud account compromise.

# Which one should you use?

For most accounts, synced passkeys are fine. They are a real upgrade over passwords, they shut down phishing in the same way hardware keys do, and they remove the friction that kept FIDO2 adoption low for a decade. If your bank, your email, and your social accounts all let you switch from password plus SMS to a synced passkey, that is a good thing to do.

For high assurance accounts, a hardware key is still stronger. The accounts where this matters in practice are:

* Your password manager itself. If the password manager is the gate to everything else, treat it like one.
* Your primary email account, especially if it gates account recovery for other services.
* Identity provider accounts (Microsoft Entra ID, Google Workspace, Okta) for organisations.
* Accounts protecting code signing, cryptocurrency, or other irreversible assets.

The right answer for most people is to use both: a synced passkey for the majority of accounts, and a hardware key for the small set of accounts where you do not want a cloud breach to mean a credential breach.

# Does this change what hardware key I should buy?

Mostly no. Every FIDO2 hardware key in the catalog can hold passkeys. Capacity varies, with older keys holding around twenty five and current keys holding from one hundred to three hundred discoverable credentials, but anything you buy today will hold more passkeys than most users actually create.

What has changed is that buying a key is now even more obviously a good idea. The passkey ecosystem has matured. Sites that support passkeys also support hardware key passkeys, because the protocol is the same. The "I do not want to be locked into Apple or Google" argument now points at hardware keys more clearly than it did when synced passkeys were the only practical option.

Buy two keys. Register them both. Use synced passkeys for everything that does not matter much. Use the hardware keys for everything that does. That is the 2026 setup.
