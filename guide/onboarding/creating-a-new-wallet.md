---
layout: guide
title: Creating a new wallet
description: Steps to take when creating a new wallet
parent: Onboarding
nav_order: 2
permalink: /guide/onboarding/creating-a-new-wallet/
main_classes: -no-top-padding
---

# What is a bitcoin wallet?

First, bitcoin wallets are not analogous to their namesakes. Physical wallets are places to store physical currency, credit cards, IDs, and so on. Bitcoin wallets don't actually store bitcoin.

Instead, a bitcoin wallet contains the "private keys" to your bitcoin, the bitcoin is located on a network that contains a communally sustained public ledger with a record of everyone's transactions and balances (so think of bitcoin wallets more like keychains). Like regular keys on a keychain, these keys can be copied. For example, if you gave someone a copy of your house keys, they could get into your home. Likewise, if someone has a copy of your private key, they can access your funds. This makes private key management one of the most important considerations of any bitcoin owner.

There are a few different types of [wallets](https://bitcoin.design/guide/glossary/#wallet) that let you send, receive, and store bitcoin.

{% include tip-open.html %}

The wallet creation process is an excellent place to break things up into different activities, events, and tasks. For example, you might want to dedicate multiple screens to generate a recovery phrase and explain why it is essential.

{% include tip-close.html %}

# Creating a new wallet

After downloading a wallet application, users are typically presented with the option of either creating a new wallet or restoring an existing one. Obviously, first-time users will be going through the flow of creating a new wallet.

Once an individual selects “create a new wallet”, it’s common for beginner friendly applications to first present informational carousels that provide a high level overview on the implications, benefits, and responsibility that comes along with having a non-custodial wallet. This moment is a great place to explain that, unlike traditional centralized financial products, a user’s “account” information cannot be recovered by the respective company. Rather, it is up to the user to safely protect their wallet information. While this may sound daunting to first-time users, it’s crucial that these caveats are not hidden. Doing so may severely compromise the safety of their funds, as their default assumptions and behaviors could potentially mimic how they typically use centralized applications (for example, feeling like it is OK if they forget their account information because they can contact customer support to help them recover it). According to a study conducted by Ekandari et al about the usability of cryptocurrency wallets, it became clear that users struggled greatly with technical terminology and feeling as though they had a lack of guidance during wallet setup. By walking users through a short set of carousels that clearly frame these Bitcoin-specific features, users will feel well-equipped to confidently navigate and use your wallet.

[Prototype](https://www.figma.com/proto/oLJlzjXqgoU7efgXJM8FlK/Onboarding-Prototypes?node-id=1%3A4&viewport=125%2C332%2C0.4993551969528198&scaling=min-zoom)

This prototype exhibits the typical first screen that users are shown after downloading a Bitcoin wallet, followed by an outline of suggested informational carousels that explicitly lay out/guide users on the unique features of non-custodial wallets to make sure they understand these caveats. These screens suggest talking about ownership of their “account”, explicitly stating the recovery mechanism that the respective wallet uses, and security measures that they should take to protect their wallet.
