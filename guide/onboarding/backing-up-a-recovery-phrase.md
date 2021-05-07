---
layout: guide
title: Backing up a recovery phrase
description: Handling recovery phrases during onboarding
parent: Onboarding
has_children: true
nav_order: 3
permalink: /guide/onboarding/backing-up-a-recovery-phrase/
main_classes: -no-top-padding
---

# Backing up a recovery phrase

When a user generates a new wallet, it results in creating something called a private key (also known as a recovery phrase). A [recovery phrase]({{ 'guide/glossary/#recovery-phrase' | relative_url }}), is a group of 12 or 24 words that let users recover funds if wallet access is lost. Likewise, users who lose both their recovery phrase and wallet access permanently lose their bitcoin. Arguably, this creates one of the toughest design problems within the space.

<div class="center" markdown="1">

{% include image.html
   image = "/assets/images/guide/onboarding/backing-up-a-recovery-phrase/verify-recovery-phrase.png"
   retina = "/assets/images/guide/onboarding/backing-up-a-recovery-phrase/verify-recovery-phrase@2x.png"
   width = 250
   height = 250
   alt-text = "Recovery phrase interface"
   caption = "Typical recovery phrase UI from the [UI Kit](Bitcoin Wallet UI Kit)"
   layout = "float-left-desktop -background -shadow"
%}

When new users are presented with a recovery phrase, they are often asked to write 12 or 24 words on a piece of paper and store it safely. This kind of recovery scheme can create an unfamiliar and frustrating onboarding experience. It also poses potential threats to the safety of their funds, as new users may not know how to properly store their recovery phrase, increasing their risk of losing it. It also a creates decent amount of friction, ultimately driving new users away from self-custodying their bitcoin.

Regardless of the type of scheme you decide to go with, it’s crucial to be explicit about how your product is handling key management.

</div>

Recent [studies](https://voskart.de/pdf/bits_under_mattress.pdf) show users are often confused or unaware of where their private keys are being stored, ultimately causing inadequate risk assessment and poor storage behavior. This risk of user negligence may be avoided with transparent messaging around the scheme your wallet is using.

> New-to-crypto users often expect a recovery mechanism that allows them to “regain access to their funds in the case that they lose their seed phrase.”
>
> <cite>As researched by <a href="https://voskart.de/pdf/bits_under_mattress.pdf">Voskobojnikov et al</a></cite>

In the [private key management]({{ 'guide/private-key-management/introduction/' | relative_url }}) chapter, we recommend using an automatic cloud backup for newer users. Users can simply press a button to have their recovery phrase backed up to the cloud without having to physically write down and store it. On top of this, the onboarding process is then sped up and less cumbersome. This type of gateway gives a beginner security without overwhelming them with unfamiliar onboarding actions.

However, there may be times when it is necessary to use a manual backup alternative, as it can be low tech and easily accessible.

The next sections will look at some UI considerations for [automatic cloud backups]({{ 'guide/onboarding/backing-up-recovery-phrase/automatic-cloud-backups' | relative_url }}) and [manual backups]({{ 'guide/onboarding/backing-up-recovery-phrase/manual-backups' | relative_url }}).