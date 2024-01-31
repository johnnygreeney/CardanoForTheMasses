# Chapter 9: Voltaire

*‘No problem can withstand the assault of sustained thinking’* ― Voltaire

## Money is social
With a few noteworthy exceptions most blockchains have made no provision for future upgrades. The capacity to effectively drive a soft or hard fork is critical to a cryptocurrency’s long-term viability. As a result, investors are unlikely to spend millions of dollars on protocols whose roadmap and participants are fleeting, petty, or extremist. There must be an efficient procedure for forming agreement on a vision for the underlying protocol’s evolution. Fragmentation might split the group apart if this process is difficult.

Cryptocurrencies are an excellent illustration of money’s social component. When comparing Bitcoin, Litecoin and Dogecoin merely on the basis of technology, there is little difference between the three. Despite this, both Litecoin and Dogecoin have relatively large market capitalizations, active communities, and their own social agendas.

It might be claimed that a significant portion of a cryptocurrency’s worth is generated from its community, how they use their funds, and how involved they are in the currency’s progress. Adding to the idea, other currencies, such as Dash,[^01] Tezos[^02] and Polkdot[^03] have built methods directly into the protocol to allow its users to vote on what should be prioritized for development and funding.

The huge variety of cryptocurrencies also demonstrates their social aspects. Fragmentation and forks result from disagreements over philosophy, monetary policy, or even petty squabbling amongst the core developers. CH at ScotFest 2022:

> People fall out over values, not facts

Unlike their digital cousins, fiat currencies tend to weather political upheavals and local disputes without a currency crisis. It seems that certain aspects of legacy systems are absent from the crypto sector. Cardano’s stance is that protocol users need incentives to understand the social contract that underpins their system and the opportunity to suggest modifications in a constructive manner. This independence applies to every facet of a value exchange system, from market regulation to project funding. However, it cannot be mediated by central actors, nor does it need any credential that may be co-opted by a privileged few.

Funding invariably dries up, regardless of the success of a crowdsale[^04] to bootstrap development. As a result, Cardano contains a treasury that reduces inflation and transaction fees over time. Through a ballot mechanism, any user should be able to seek funds from the trust, and stakeholders should vote on who becomes a beneficiary. By creating a discussion about who should be financed, the process produces a positive feedback loop like those found in other cryptocurrencies with governance systems, such as Dash. Healthy dialogue ensures that the community is always assessing and arguing its views ahead of crucial decisions.

Long running and, in many instances, unresolved disagreements about the technical and moral direction of the codebase have plagued Bitcoin with its block size debate, Ethereum with the DAO split, and a slew of other cryptocurrencies. Many of these conflicts, as well as the splitting of the community that occurs when action is taken, can be attributed to the absence of any mechanism for implementing change.

Looking to lessons from the past, Bitcoin’s adoption of (SegWit) Segregated Witness[^05] could have been handled a lot better.[^06] Did the DAO attack[^07] really have to result in the hard fork on Ethereum? Could it have been managed better so there was not such a dramatic community breakdown?[^08]

In the worst-case scenario, moral authority to act might simply devolve to whomever has the developers, infrastructure links, and money, rather than the community’s best interests. It’s difficult to gauge if actions are valid if a major segment of the community is unavailable, or disengaged owing to poor incentives.[^09]

Some cryptocurrencies like Tezos have a model where the cryptocurrency protocol is handled as a constitution, with three parts (Transaction, Consensus, and Network) and a set of explicit rules and procedures for updating the constitution. However, there is still a lot of work to be done on incentives and how to represent and update a crypto protocol using a formal language.

IOG have been researching governance in crypto for years. They have written papers as far back as 2017 on proposing a treasury for Ethereum Classic.[^10] Another paper, authored out of Lancaster University,[^11] focused on the concept of a treasury system and a viable, democratic method to long-term development financing for Cardano.

Formal methods, machine comprehensible specifications, and combining a treasury with this process for financial incentives are just some of the solutions IOG pursued. Looking back now, it’s clear they were putting the chess pieces in place, to create the apparatus necessary for the *Age of Voltaire* vision presented at ScotFest[^12] in November 2022. More on this later. 

## Cardano Improvement Proposals (CIPs)

One of the early governance pieces implemented in November 2020 was CIP 0001,[^13] which explains what a CIP is. Anyone who has ideas for enhancing Cardano may present them in the form of CIPs (Cardano improvement proposals). CIPs are a means of formally proposing enhancements in a consensus-based manner. They are an essential component of Cardano governance, even though they are not binding, nor a requirement for treasury or protocol modifications. 

Technically, the first ever CIP was created in October 2019 and subsequently became CIP-1852. It extends BIP44[^14] and was written to document how Cardano wallets handle keys and addresses. This document existed even before the CIP process was created. It was named CIP-1852 by Sebastien Guillemot after the year Ada Lovelace died (her birth year, 1815, is used in the cointype field). 

A CIP follows a standard format: the proposal structure is templated to make debate and evaluation easier. This allows other members of the community to weigh in on improvement recommendations, or issues in a proposal. CIPs are kept as text files in a versioned GitHub repo,[^15] and their revision history provides the proposal's historical record. For those who aren’t on GitHub, cips.cardano.org is an auto-generated sister site maintained by the Cardano Foundation.

There are three different types[^16] of CIP:

1. A **Standards Track CIP** is a modification that impacts Cardano implementations. Examples: a network protocol update, or basically any other change that affects the compatibility of Cardano applications. CIPs on the Standards Track have two parts: a design doc and a reference implementation.

2. A **Process CIP** outlines a Cardano-related process or suggests a modification to one. Process CIPs are similar to Standards Track CIPs, however they are used for topics other than the Cardano protocol. They usually need community approval; thus, unlike Informational CIPs, they are more than suggestions that users are not free to disregard.

3. An **Informational CIP** discusses a Cardano design issue or gives broad Cardano community standards or information, but it does not propose anything new. Users and implementers are entitled to disregard Informational CIPs, or follow their advice because they do not necessarily reflect a Cardano community consensus or suggestion.

Every CIP has the following format: Preamble, Abstract, Motivation, Specification, Rationale, Path to Active, Copyright. The concept is developed as a written proposal and submitted as a pull request[^17] to the CIP repository after initial discussion and feedback. The updated Draft CIP is then publicly processed in the following manner:

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig91.png "figure 9.1")
<br>**Figure 9.1:** CIP workflow from CIP0001

CIPs are processed in a semi-formal manner: Editors of CIP proposals meet on a regular basis to discuss and assess ideas. Meeting minutes are available to the public,[^18] and meetings are held every two weeks. Authors are encouraged to contribute and offer comments, and discussions often take place simultaneously in the Cardano forum CIPs section[^19] and/or in the GitHub pull requests. If you have designs on becoming a CIP editor, you should read Robert Phair’s blog about his experience in the role.[^20]

Consider the CIP repository to be a collection of useful tools - some may play well together, while others will not. You have complete control over which CIPs your implementation adheres to. The community will lean toward some more than others, new ones should be submitted as Cardano grows.

**Notable CIPs:**

CIP 1 - CIP process 

‘A Cardano improvement proposal (CIP) is a formalized design document for the Cardano community, providing information or describing a new feature for the Cardano network, its processes, or environment in a concise and technically efficient manner.’ CIP 1 specifies three statuses: Proposed, Active and Inactive and each CIP falls into a category.[^21]

CIP 9 - Protocol Parameters

‘This CIP is an informational CIP that describes the initial protocol parameter settings for the Shelley era of the Cardano blockchain, plus the changes that have been made. It is intended to serve as a historic record, allowing protocol parameter changes to be tracked back to the original settings.’

CIP 25 - NFT Metadata Standard

This proposal defines an NFT Metadata Standard for Native Tokens.

CIP 27 - CNFT Community Royalties Standard

A community standard for royalties' functionality, that does not require smart contracts to implement.

CIP 30 - Cardano dApp-Wallet Web Bridge

This CIP describes the communication bridge allowing dApps to interface with Cardano wallets.

CIP 31 - Reference Inputs

‘We introduce a new kind of input, a reference input, which allows looking at an output without spending it. This will facilitate access to information stored on the blockchain without the churn associated with spending and recreating UTXOs.’

CIP 32 - Inline datums

‘We propose to allow datums themselves to be attached to outputs instead of datum hashes. This will allow much simpler communication of datum values between users.’

CIP 33 - Reference scripts

‘We propose to allow scripts ("reference scripts") to be attached to outputs, and to allow reference scripts to be used to satisfy script requirements during validation, rather than requiring the spending transaction to do so. This will allow transactions using common scripts to be much smaller.’

CIP 50 - Liesenfelt Shelleys Voltaire Decentralization Update 

Proposed by Dr Michael Liesenfelt, this CIP discusses the justification, methods, metrics, and implementation schedule to increase Cardano’s decentralization.

CIP 68 - Datum Metadata Standard

This proposal defines a metadata standard for native assets making use of output datums not only for NFTs but any asset class.

CIP 79 - Implement Ouroboros Leois to increase Cardano throughput

This CIP discusses the implementation of *Ouroboros Leios*. 
 
CIP1694 - A First Step Towards On-Chain Decentralized Governance

A proposal for Cardano's on-chain governance system to support the new requirements for Voltaire. The busiest CIP to date, based on comments and updates. See 1694.io which presents the CIP in a tidier format, maintained by LIDO Nation.

CIP999 (read as ‘CIP minus 1’) - Cardano Problem Statements (CPS)

CPSs complement CIPs. CIP999 explains the need for CPSs, their set structure, statuses and criteria for their success. CPSs were introduced to simplify the process when explaining the problem statement of complex CIPs, replacing the more elaborate ‘*motivation*’ section. They may also exist as standalone ‘requests for proposals from ecosystem actors who've identified a problem but are yet to find any suitable solution’.


![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig92.png "figure 9.2")
<br>**Figure 9.2:** CIP workflow from editors’ perspective

## What is Project Catalyst?





**_To be uploaded soon..._**



[^01]: **Dash** is an open source cryptocurrency and is a form of decentralized autonomous organization (DAO) run by a subset of users, called ‘masternodes’. It is an altcoin that was forked from the Bitcoin protocol. The currency permits fast transactions that can be untraceable.
[^02]: **Tezos** (ticker: XTZ) is a decentralized blockchain founded by Arthur Breitman and Kathleen Breitman. The Breitmans also founded Dynamic Ledger Solutions (DLS), a company primarily focused on developing Tezos technology and owns the Tezos Intellectual property. The currency was launched in an initial coin offering (ICO) on July 1, 2017.
[^03]: Polkadot OpenGov, polkadot.network/features/opengov/
[^04]: **Crowdsales** are a popular use for Ethereum; they let you allocate tokens to network participants in various ways, mostly in exchange for Ether. They come in a variety of shapes and flavors.
[^05]: Segregated Witness, or SegWit, is the name used for an implemented soft fork change in the transaction format of bitcoin. 
[^06]: The Tale Of SegWit: Controversy, Civil War & Adoption, blog.btse.com/segwit/ 
[^07]: Understanding the DAO attack, coindesk.com/learn/2016/06/25/understanding-the-dao-attack/
[^08]: Ethereum fall out, fortune.com/2016/09/04/ethereum-fall-out/
[^09]: Incentive: a method of encouraging members to participate in the network by providing them with a return proportionate to their efforts.  By promoting persistent, active, and robust engagement, incentives strive to maintain equality and fairness in a dispersed network of participants. The incentives necessary in Cardano’s incentives model are calculated using game theory.
[^10]: Kaidalov, Kovalchuk, Nastenko, Rodinko, Shevtzov, Oliynykov (2017), ‘A proposal for an Ethereum Classic Treasury System’, iohk.io/en/research/library/papers/a-proposal-for-an-ethereum-classic-treasury-system/
[^11]: Zhang, Oliynykov and Balogun (2019), ‘A Treasury System for Cryptocurrencies: Enabling Better Collaborative Intelligence’, eprint.iacr.org/2018/435.pdf 
[^12]: IO Scotfest: The age of Voltaire, youtube.com/playlist?list=PLnPTB0CuBOBxjkB8DdMhy57MriBCHT1RM
[^13]: CIP-0001: Cardano Improvement Proposals, github.com/cardano-foundation/CIPs/tree/master/CIP-0001
[^14]: BIP44 (Bitcoin Improvement Proposal), github.com/bitcoin/bips/blob/master/bip-0044.mediawiki
[^15]: CIP repo, github.com/cardano-foundation/CIPs
[^16]: Make it even better: Cardano's Improvements Proposals, cardanofoundation.org/en/news/make-it-even-better-cardanos-improvements-proposals
[^17]: Pull requests are a feature specific to GitHub. They provide a simple, web-based way to submit your work (often called “patches”) to a project. It's called a pull request because you're asking the project to pull changes from your fork.
[^18]: CIP biweekly meetings, github.com/cardano-foundation/CIPs/tree/master/BiweeklyMeetings
[^19]: Cardano Forums CIP section, forum.cardano.org/c/english/cips/12
[^20]: Cardano Improvement Proposals (CIPs) — Introduction from an Insider, rxphair.medium.com/cardano-improvement-proposals-cips-introduction-from-an-insider-7b2f7cc94d01
[^21]: CIP-0001 categories, github.com/cardano-foundation/CIPs/tree/master/CIP-0001#categories
[^22]: Cardano IdeaScale, cardano.ideascale.com/
[^23]:
[^24]:
[^25]:
[^26]:
[^27]:
[^28]:
[^29]:
[^30]:
