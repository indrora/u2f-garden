---
Title: Why use U2F Tokens?
---

When you log into a website, you're probably used to using your username and password.
Increasingly, however, phishing and other social engineering attacks are getting better and better.
In a modern world, hardware security tokens like U2F tokens help keep attackers from taking advantage of us.

# What is Two-Factor authentication?

Two factor authentication (2FA) is a way that websites can secure accounts.
In order to log in, you must present two forms of authentication:

* Something you know (a *password*)
* Something you have (such as a one-time password)
* Something you control (such as a phone app)

Security standards organizations like NIST, who set the standards for security in organizations like the Department of Defense and other government organizations
have suggested moving away on the reliance on things you memorize, like passwords, and further onto controlled authentication devices.

# How U2F tokens work

U2F tokens take advantage of a security technique called [Public Key Cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography), the same kind of cryptography that secures the web, credit cards, and more.
This form of cryptography uses two keys: a public key and a private key.
The private key is kept secret, but the public key is given out freely.
Encrypting something with one key can only be decrypted with the other.
If something was encrypted with the private key, it's considered *signed*. 
These signatures are used to verify the identity of a key: in web security, a portion of a certificate is signed by a certificate authority such as VeriSign or Let's Encrypt 

Every time you register a token with a website or application, the key generates a new, unique cryptographic key for that site, associated with the domain.
Part of that key, the "public" part, is returned by the key, stored by other party.


# A history of Two-Factor authentication

Cras nec quam lobortis, commodo arcu in, fermentum urna. Nunc accumsan ligula consectetur, pellentesque tortor eu, malesuada lacus. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus sagittis ut augue id egestas. Nunc placerat sapien vel massa rutrum tincidunt. Maecenas blandit lacus et erat auctor dapibus. Phasellus et blandit dolor. Curabitur molestie aliquam libero, eu tempor leo ultricies id. Fusce iaculis libero in orci auctor ultricies. Nunc faucibus auctor nisl, at lacinia metus luctus at. Aenean a risus in ipsum ullamcorper molestie eget in massa. Suspendisse lacinia, lorem nec sollicitudin tincidunt, justo arcu pretium ante, finibus mollis purus risus id dolor. Maecenas iaculis mauris in est facilisis, ac dignissim risus vulputate. Donec facilisis sagittis purus, ut suscipit magna consequat in.


## Generation 1: Text messages

Historically, sites that implemented one-time passwords by sending SMS messages whenever you went to log in, requiring you to enter a code that was sent to you. 
This mechanism is still used, but isn't recommended: attacks such as [SIM swaps](https://www.consumer.ftc.gov/blog/2019/10/sim-swap-scams-how-protect-yourself) allow an
attacker to take over your account and [SMS redirection](https://www.vice.com/en/article/y3g8wb/hacker-got-my-texts-16-dollars-sakari-netnumber) allows an attacker to silently
redirect your SMS messages to someone for under US$20. 

## Generation 2: Events, Time, and Apps, oh My!

More recently, tools such as Hash-based One Time Passwords (HOTP), sometimes called Event-based OTP, and Time-based One Time Passwords (TOTP) provide a way to circumvent this:
by using an application on your phone, computer, or a hardware code generator, you and the service you're logging into generate the same code derived from a shared value, called a "Secret". Applications such as Google Authenticator and hardware tokens such as those made by RSA and Gemalto are common examples of time and event based one-time password applications and hardware.

While these are more secure, since an attacker can't intercept the code in flight to you, these mechanisms fall victim to phishing attacks: If an attacker can trick you into entering your One-Time-Password into their fake log-in page, then you've given them everything they need in order to be you, so long as they use that information in a relatively short span of time. These sorts of attacks are hard to spot in the wild unless you have a very keen eye, and attackers are getting better and better at replicating the interfaces of banks, services, and other sensitive online spaces. 

Simultaneously, app-based authenticators became more popular. These applications 

## Generation 3: Hardware tokens.