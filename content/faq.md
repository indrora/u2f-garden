---
title: Frequently Asked Questions
draft: false
---

Here are some common questions people ask:

# Why should I use a security token over an SMS authentication tool?

SMS messages can -- and have -- been intercepted in the past. Attackers use techniques like [SIM swapping](https://en.wikipedia.org/wiki/SIM_swap_scam)
to hijack messages and even phone calls. 

Learn more about

* [SIM Swapping attacks and what the FCC is doing about them](https://krebsonsecurity.com/2021/10/fcc-proposal-targets-sim-swapping-port-out-fraud/)
* [Weaknesses in mobile telephone networks](https://www.wired.com/2017/05/fix-ss7-two-factor-authentication-bank-accounts/)

# Do I need a different token for every site?

You don't need a different token for every site. Because modern 2FA tokens don't need to store much of anything on them, they can be used for a near infinite number of sites for the vast majority of cases. 


# What if I lose my token? What about backups?

This depends on the service, but you will need to add your new token to each service. Many services will require you to recover your account in some form or fashion in order to add a new token.

Some services allow you to have more than one token associated with your account at a time. Having a second token for these services that you keep in case of emergency is advisable.
Many services also provide *backup* values: When something goes wrong, these make up your backup plan.

# Do tokens replace password managers?

No, tokens don't replace password managers. Password managers are, however, buffered by tokens. 

