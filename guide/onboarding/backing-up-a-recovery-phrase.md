---
layout: guide
title: Backing up a recovery phrase
description: Suggested recovery phrase backups when onboarding
parent: Onboarding
nav_order: 3
permalink: /guide/onboarding/backing-up-a-recovery-phrase/
main_classes: -no-top-padding
---

# Backing up a recovery phrase

When a user generates a new wallet, it results in creating something called a private key (also known as a seed phrase, backup seed phrase, or recovery phrase). We dive into different names for this concept later in this section. [A recovery phrase]({{ 'guide/contribute/#recovery-phrase' | relative_url }}), to use that example, is a group of 12 or 24 words that let users recover funds if wallet access is lost. Likewise, users who lose both their recovery phrase and wallet access permanently lose their bitcoin.

Since new users are unfamiliar with whipping out a pen and paper to write and safely store 12-24 words, this kind of recovery scheme can create an unfamiliar and frustrating onboarding experience. It also poses potential threats to the safety of their funds, as new users may not know how to properly store their seed phrase, increasing their risk of losing it. These kinds of recovery phrase backups—the type that requires writing down 12-24 words then entering them back into the wallet—can create a decent amount of friction, ultimately driving new users away from self-custodying their bitcoin.

Regardless of the type of scheme you decide to go with, it’s crucial to be explicit about how your product is handling key management. According to recent studies, users are often confused or unaware of where their private keys are being stored, ultimately causing inadequate risk assessment and poor storage behavior (x). This risk of user negligence may be avoided with transparent messaging around the scheme your wallet is using.

In the private key management chapter, we recommend using automatic cloud or “seedless” backup for new users. According to [research][^1] about users’ experiences with crypto wallets, new users tend to base their expectations off of traditional financial systems. As stated by Voskobojnikov et al, they often expect a recovery mechanism that allows them to “regain access to their funds in the case that they lose their seed phrase”. This reveals a desire to not be the sole individual responsible for keeping their seed phrase safe. With a seedless backup scheme, users can simply press a button to have their recovery phrase backed up on the cloud without having to physically write down and store their seed phrase. They are never exposed to their recovery phrase, ultimately interacting with an interface that abstracts away from this foreign concept. On top of this, the onboarding process is then sped up and less cumbersome. This type of gateway gives a beginner security without overwhelming them with unfamiliar onboarding actions. However, automatic cloud backups should not be considered when storing high-value amounts or when the loss from theft is higher than the loss from negligence.

Lastly, users who are new enough to require an automatic cloud backup as a solution should consider how they reveal a recovery phrase if at all. Displaying a recovery phrase at this point could compromise it.

{% include tip-open.html %}

Before automatically backing up a recovery phrase, make sure the user knows what they are about to do. Once the backup is complete, provide a summary and some reassurances before moving on. This is a good place for loading interactions and animation.

{% include tip-close.html %}

Although we recommend using a seedless backup scheme for beginner wallets, we understand that some may opt into a manual seed phrase backup scheme. A later section outlines how, if necessary, you should design an onboarding experience that requires users to manually backup their seed phrase.

## Option 1: Seedless Backup
### How it Works

Otherwise known as an automatic cloud backup, a seedless backup scheme is the most favorable way to design wallets geared towards first-time users. According to research conducted by Abramova et al, crypto rookies perceive themselves as “incapable of self-managing keys” (x). In a sense, a seedless backup provides users with the feeling that they can rely on their cloud provider to regain access to their funds rather than putting the responsibility of properly storing their seed phrase on themselves. By being able to backup a seed phrase with one touch of a button, it also provides extremely low onboarding friction. With a seedless backup design, users don’t have to go through the cumbersome and unfamiliar task of whipping out a pen and paper to record and store their seed phrase.

At a high level, the user’s key is encrypted and backed up on their respective device/cloud storage provider. In the case that their device is lost, stolen, or broken, the user can simply log into their Apple or Google account to regain access to their funds. To learn more about the technical details, hop over to the Private Key Management section on this topic.

### How to Discuss It/Explain It
Because backing up a user’s seed phrase on their iCloud (or respective cloud storage provider) is rather speedy, this can be a straightforward step within onboarding.

However, it’s important that you still provide context and implications of what this means. An appropriate way to do this is to explicitly explain within the onboarding carousels that a user’s seed phrase (we recommend using a different word, which we lay out in another section) is stored on the cloud; this means that, if they lose or break their device, they can regain access to their funds by logging into their respective cloud account on a different device. On a similar note, it’s crucial that you also explain that if someone else knows their cloud account information, they can gain access to their funds, too.

To ensure that users understand that they are backing up their wallet information to their respective cloud storage provider, we recommend that you include a screen with a CTA button that says something along the lines of, “Backup to Cloud”. Although it may seem unnecessary, this simple step reiterates what is happening, furthermore educating them on where their wallet information is going and how they can regain access to their funds if needed.

[*ILLUSTRATION*](https://www.figma.com/file/oLJlzjXqgoU7efgXJM8FlK/Onboarding-Prototypes?node-id=2%3A94)
This prototype exhibits a screen and onboarding step that shows a user that their wallet is using a seedless backup. It’s purpose is to use the CTA to stress that they are, in fact, backing up their recovery phrase to the cloud. It also explains how to recover your account and particular consequences that come with this recovery scheme.

### Trade Offs
Although this scheme is the easiest way to onboard first-time bitcoin owners, these benefits come with some caveats.

In today’s day and age, backing up account information to the cloud is a familiar motion to go through. By not making users manually store their seed phrase, we decrease the risk of self-inflicted loss of funds. On the contrary, automatic cloud backups put less pressure and responsibility on the user.

While this is the easiest way for users to set up a wallet, seedless backups bring in the potential threat of malicious third party access. If a user’s cloud account is hacked or they forget their cloud login information, their funds could be compromised. Additionally, by bringing cloud storage providers into the equation, we assume that users trust their providers. This also raises the question of decentralization: a guiding principle of the bitcoin space. By storing a user’s seed phrase on the cloud rather than directly giving it to them, we go against the saying, “not your keys, not your crypto”.

{% include tip-open.html %}

To grant users some ownership of their keys, you can create an optional manual backup within settings. A great way to do this is by framing it as an extra layer of security, or a good alternative in the case that the user loses access to their cloud account/if they feel uncomfortable trusting their provider.

{% include tip-close.html %}

## Option 2: Manual Backup
### How it Works

As previously stated, onboarding flows that require users to manually back up their seed phrase typically shows users their respective 12-24 word phrase, expecting them to then write it down on a piece of paper and store it in a safe but memorable location. In the case that a user’s device breaks or  is stolen, the user can recover their funds and wallet by chronologically and correctly entering their seed phrase. The private key management section dives further into the technical details of this scheme if interested in learning more.

Once again, we do not suggest using this scheme if you are creating a wallet built for first-time crypto users; this group is often unfamiliar with the practice of physically writing down and safely storing such crucial information. This novel onboarding step often results in new users unsafely storing their phrase (such as taking a screenshot on their mobile device) or being unsure on where/how to store it. However, many wallets stand by the ethos that users should be the ones to know and own their keys, furthermore favoring the act of users manually backing up their seed phrase. If you are designing a wallet that falls into this category, the following sections outline how to best go about this with crypto newbies in mind.

### Unveiling a Seed Phrase
If your application requires users to manually backup their seed phrase, it’s crucial that your onboarding process provides sufficient information to ensure that users understand the weight that seed phrases hold in determining the safety of their funds.

Specifically, the onboarding carousels that we previously mentioned are a great place to prep and explain to users that they will be given a seed phrase. While some wallets skip presenting a user with their seed phrase during onboarding, we highly suggest doing so. Unveiling a user’s seed phrase within the initial onboarding process allows users to pause, internalize what a seed phrase is, and ensures that they do not neglect this step later on. A mistake that some current wallets make is hiding the backup process within their app settings. Unfortunately, this decision could potentially compromise user’s funds, as first-time crypto owners would not think to seek out this step.

{% include tip-open.html %}

If you really want to skip showing a user their seed phrase during the onboarding process (which we advise against), create an interaction (i.e. a vibration, modal pop-up, or blocking users from clicking anything) that prompts users to “back up” their seed phrase before making any transactions to ensure that they do not skip the step of writing it down. Muun Wallet does a great job of guiding users through backing up their wallet after onboarding.

{% include tip-close.html %}

[*ILLUSTRATION*](https://www.figma.com/proto/oLJlzjXqgoU7efgXJM8FlK/Onboarding-Prototypes?node-id=29%3A387&viewport=50%2C281%2C0.3386879861354828&scaling=min-zoom)
This prototype exhibits some points we believe are important to touch on before presenting a user with their seed phrase.

Because seed phrase is a crypto-specific term, Bitcoin newbies will likely not know what it is. Swapping out the term seed phrase for a proper noun that drills in the fact that this set of words is used to restore/recover their account and/or is something that should be kept secret is a great way to introduce this otherwise unfamiliar concept. Existing wallets that are geared towards new users often use the following terms instead of seed phrase. We recommend you do the same:
 - Recovery phrase (the most popular)
 - Recovery key
 - Recovery words
 - Backup phrase
 - Secret phrase
Because recovery phrase is the most common term, we suggest using it to create consistency across applications. This can build stronger mental models for users.

{% include tip-open.html %}

Whatever term you decide to use within your application, it’s important to be consistent with it. For example, toggling between the words “recovery phrase” and “recovery key” may be extremely disorienting and confusing to users. Choose a term and stick with it.

{% include tip-close.html %}

When introducing the concept of a seed phrase within the onboarding process, be succinct and clear in explaining what a seed phrase is, how to store it, and how to use it. This can be done at a high level. It’s not necessary (and may even be harmful) to dive into the nitty-gritty technical details. Rather, focus on making a user feel empowered and prepared to handle their seed phrase before showing it to them. Examples of copy that we recommend you include in the onboarding process before unveiling a user’s seed phrase can be found below. Swap out recovery phrase for whatever term you decide to use for seed phrase:
 - “You will be shown your recovery phrase on the next screen” → preparing a user for what they are about to see
 - “Your recovery phrase is a group of 12 words and is the only way to access your wallet if your phone is lost or stolen” → explaining the purpose
 - “If you lose your recovery phrase, you will no longer be able to access your wallet. Never share your recovery phrase with anyone. Anyone who has it can access your funds” → explaining the consequences of their behavior
 - “We recommend writing these words down in order on a piece of paper and storing it somewhere safe that you will remember” → guiding users on how to handle it

{% include tip-open.html %}

Providing users with printable, designated materials (like Monero) to write down their seed phrase can instill a sense of trust, organization (especially if they have multiple wallets), and guidance within users. It may also encourage them to treat this paper with importance, rather than quickly scribbling it down on a random piece of paper.

{% include tip-close.html %}

Drilling in the larger consequences of what it means to interact with a non-custodial product is crucial during these first interactions with a wallet. Education within these beginning stages will empower users to make smart decisions, furthermore informing how they understand and handle the safety of their funds.

{% include tip-open.html %}

Regardless of the option you decide to run with, it’s important that you explicitly instruct users to number each word (i.e. 1. sand 2. purple 3. flower). Manually backing up seed phrases typically asks users to recount, for example, the fifth word. It’s a bit of a pain for users to count which word corresponds to a particular number if they are not numbered initially.

{% include tip-close.html %}

### Ways to show It
After explaining to users what a seed phrase, the next step within the onboarding process is to actually show it. How a wallet decides to deliver this– whether it’s one word at a time, or all at once– can implicitly determine what subsequent actions a user takes to store their mnemonic and, in turn, the safety of their funds. When showing a user their seed phrase, the goal is to encourage them to write it down on a physical piece of paper. You can discourage users from taking a screenshot by showing a warning modal if they do, or explicitly stating that they should not do that.

Option 1: One by One
In a one by one design, users are given their seed phrase one word at a time. Users are then prompted to swipe/click through each word to complete their viewing.
Pros: By forcing users to go through a physical action of viewing the next word, the chance of someone accidentally skipping over a word decreases. Giving a user time on each word encourages them to ruminate on it, potentially increasing their chance of writing it down. Additionally, it discourages users from screenshotting or copying/pasting their seed phrase.
Cons: This would be a time consuming step if one’s seed phrase is 24 words. This length could cause frustration.
Wallets that do this: BitPay
*ILLUSTRATION*


Option 2: In Columns/Groups
Another way to unveil a user’s seed phrase is in batches/groups. In this design, the wallet splits the 12-24 word seed phrase into ~3-4 groups, each group containing 3-12 words.
Pros: If your wallet uses a 24-word mnemonic, splitting it into groups can make seed phrases more digestible and less overwhelming. Organizing into smaller chunks could also help with word association, as a user might remember the smaller batches of words.
Cons: Depending on how you show these groups of words, there is room for users to falsely number the order of their seed phrase. For example, some wallets put these groups into columns, which could trip up a user if they are writing their words from left to right, or up and down. To avoid this, be sure to explicitly number the words.
*ILLUSTRATION*

Option 3: Playing on Interactions to “Uncover”
A clever way to give a user their seed phrase is by creating an interaction where they have to “uncover” it. This can entail hovering over a blurred word to reveal it, or holding down a button to show it.
Pros: By creating this design interaction, it drills in how, viewing, storing, and managing seed phrases should be a private and secret matter.
Cons: If trying to quickly view a seed phrase, it’s a bit more cumbersome to hover over each individual word.
*ILLUSTRATION*

Option 4: All at Once
Lastly, another design is to simply give a user the words in their seed phrase all at once. In this design, all words in the seed phrase are shown on 1 screen.
Pros: By presenting a user their seed phrase in its entirety, there are no surprises in how long it is and does not require them to take any further action in revealing it.
Cons: Throwing 12-24 words at a user all at once can potentially overwhelm him/her if they are not familiar with seed phrases in general. This also introduces the possibility of a user simply skipping over this 1 screen with contents that inherently determines the safety of their funds.
*ILLUSTRATION*

Confirming a Backup
After showing a user their seed phrase for the first time, the final step in onboarding “confirms” their backup. This step is a great way to ensure and test that the user in question actually stored their phrase in a way that allows them to access and recount it. This typically entails prompting them to recall the seed phrase, which can be done in multiple ways that are laid out below.
Tip: Before users can finish onboarding, create a checkbox that confirms that users understand your respective application cannot recover their seed phrase if they lose it. This drills in the importance of them properly and securely storing it, reiterating that the fate of their account is in their own hands.
*ILLUSTRATION*

Option 1: Selecting words from a bank
A common design for confirming a manual backup is to present users with a scrambled word bank that consists of the words that make up their seed phrase. Users are then prompted to select the words in the correct order.
*ILLUSTRATION*

Option 2: Manually Typing it Out
The most straightforward (yet time consuming) way to prompt a user to confirm their seed phrase is by having them manually type out their seed phrase. One way to present this is by giving them numbered fields (ranging from 12-24 depending on the length of the respective scheme) so that users can make sure they are entering it in the correct order.
Tip: Because typing each word out comes with more room for error, create a visual indicator that shows if the user is on the right track (i.e. make the box green if it is correct, make it red if it is incorrect). It can be a frustrating experience for a user to get a general warning that their phrase is not correct after having them manually type it out and force them to sleuth out where a misspelled word or wrong order occurred.
*ILLUSTRATION*

Option 3: Recall Random Word
Lastly, another way to have a user confirm that they recorded their seed phrase correctly is by asking them to select (or manually type out) a random word from their seed phrase. For example, you would ask them to “type out word number 5”, or “type out word number 11”. To ensure maximum security, make sure you do this with 3-4 different words within their phrase. This design is less cumbersome for users, but might be a pain if they did not number their seed phrase.
*ILLUSTRATION*


[^1]:[Bits Under the Mattress: Understanding Different Risk Perceptions and Security Behaviors of Crypto-Asset Users](https://voskart.de/pdf/bits_under_mattress.pdf)
