---
title: "Crypto wallets, smartphones, and other things that double as FIDO keys"
date: 2026-04-30
publishdate: 2026-04-30
lastmod: 2026-04-30
draft: false
tags: ["Editorial", "Passkey"]
author: waffles
---

The catalog focuses on dedicated FIDO security keys, the kind of small USB or NFC device whose only purpose in life is to be a hardware authenticator. There is a growing category of devices whose primary purpose is something else, but which can also act as a FIDO2 key. These are worth knowing about, both because they sometimes overlap with what you already own, and because their tradeoffs are different from a dedicated key.

# Crypto hardware wallets

Both Ledger and Trezor's current devices can act as FIDO2 keys.

**Ledger** supports FIDO2 and WebAuthn through a [Security Key app](https://support.ledger.com/article/12350325732893-zd) that the user installs on the device. As of 2026, the supported devices are the [Ledger Stax](https://www.ledger.com/) and [Ledger Flex](https://www.ledger.com/). The older Ledger Nano series had a separate FIDO U2F app, but the modern WebAuthn flow with discoverable credentials is on the Stax and Flex line. The credential lives in the EAL5+ secure element on the device.

**Trezor** supports FIDO2 and U2F across [Trezor Safe 7, Safe 5, Safe 3, and Model T](https://trezor.io/guides/bonus-tools/what-is-fido2). Trezor's flow uses the device touchscreen for confirmation. Discoverable credentials are stored on the device.

The tradeoffs are:

* You already own the device. Adding FIDO2 use is a reasonable path to a hardware backed second factor without buying another key.
* The user experience is more involved than a tap or insert. Both Ledger and Trezor expect deliberate confirmation through the device's screen and buttons, and you have to navigate to the right app.
* If you lose the device, you lose the credentials. Wallet backup phrases are seeds for cryptocurrency keys, not for FIDO credentials. Treat the FIDO use as a secondary identity that needs its own backup key.
* These devices are expensive relative to a dedicated FIDO key. If the only reason you are considering one is FIDO, buy a dedicated key.

The right use case is users who already own a wallet and want to add FIDO2 to its job description, not users buying hardware specifically for FIDO2.

# Smartphones as authenticators

Apple, Google, and Microsoft all support using a smartphone as a FIDO2 authenticator over the FIDO Alliance's hybrid transport protocol. The browser shows a QR code, the user scans it with their phone, and the phone authenticates over Bluetooth proximity. This is what produces the cross device passkey flow that has become common in 2025 and 2026.

This is convenient. It is not the same security model as a dedicated key. The phone's secure storage is shared with the rest of the operating system, and the cross device handshake creates a Bluetooth pairing that can be socially engineered in some flows. For most consumer use, it is fine. For high assurance, it is not.

# Smartphone reader devices

Vendors like [IDmelon](https://idmelon.com/) sell a small USB reader that turns a paired smartphone into a FIDO2 key for the host computer. The reader handles the USB and BLE plumbing, the phone holds the credentials. This is positioned mostly at retail and shift worker scenarios, where multiple people share a workstation and each user needs to authenticate without a personal key on the desk.

It is a real product. It is not a hardware key in the traditional sense, since the credential lives on the phone, not on the reader. Treat it as a phone authenticator with better hardware integration.

# Operating system passkeys

Windows Hello, macOS Keychain, and Android each support storing FIDO2 passkeys in the operating system's secure storage. The user verification is the same biometric or PIN that unlocks the rest of the device. From the relying party's perspective, this is indistinguishable from any other passkey holder.

If you are buying a hardware key, this is the comparison your purchase is being measured against. The OS option is free, mostly invisible, and synced through whatever cloud account the OS is signed into. The hardware key wins on isolation from cloud account compromise, on portability across operating systems, and on attestation, where enterprise relying parties want to know what kind of authenticator you used.

# What this means for the catalog

This catalog continues to focus on dedicated FIDO hardware. Wallet vendors and smartphone authenticators are adjacent, useful, and worth knowing about, but they are different products with different tradeoffs. If you came here looking for a recommendation, the dedicated key is still the right answer for users who care about phishing resistance enough to buy hardware for it.
