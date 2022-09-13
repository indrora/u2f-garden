---
title: "Hello, World!"
date: 2021-09-18T15:03:09-07:00
publishdate: 2021-09-18
lastmod: 2022-05-05
draft: false
tags: ["Editorial"]
author: indrora
---

Welcome to the U2F Garden!

The goal of the U2F Garden is to provide a guide on the many and varied U2F tokens and keys out there in the world. There's a lot of them out there and I wanted to make sure
that there was a good guide on what keys support what features. 

# Where'd this all start?

This started when I wanted to make a small adjustment to my typical SSH configuration. Normally, I'd use the PKCS11 features in my Yubikey to support this stuff. That's great,
until you realize that a Yubikey is... Expensive. And there's other USB PKCS11 tokens out there. And then OpenSSH went ahead and implemented a feature I'd wanted for some time:
U2F support!

What's U2F support give me? A bunch of stuff, actually. It means I could feasibly have a central authority for more of my SSH keys, including not having to haul around secret keys and maintain a trusted keys file all over the place. For someone like me, that's a huge boon. 

# How can I contribute? 

If you'd like to contribute, submit a pull request on [GitHub](https://github.com/indrora/u2f-garden/).
