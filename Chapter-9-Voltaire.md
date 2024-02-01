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

Another governance piece introduced in 2020 was Project Catalyst. Catalyst is a grant program that combines proposal and voting processes. Establishing a long-term future for Cardano growth began with a treasury and democratic voting in the Catalyst project. 

Catalyst is a community-driven innovation grants program that uses elements of decentralized governance to make certain decisions (i.e. the Cardano community votes to decide which proposals should receive grant funding). Funds are granted as ada, provided to IOG directly from the Cardano treasury, to administer the funding disbursements. 

There are effectively two parts to Catalyst:

1. Submitting, reviewing, and voting on proposals
2. Delivering the grant-funded project and demonstrating proof of achievement as part of the community-led accountability model

So in this way, members of the Cardano community submit proposals to deliver projects for the benefit of growing the Cardano ecosystem. The community then reviews the project proposals, providing feedback based on criteria of ‘Impact’, ‘Feasibility’, and ‘Value for Money'. Finally the community then votes on which proposals to allocate funding towards. Catalyst currently uses IdeaScale[^22] to crowdsource all proposal submissions and community reviews. ProjectCatalyst.io is a home for all things Catalyst and is where all of the funded-projects progress reporting and accountability is ultimately open and available for community members to keep track of their favorite projects they voted for. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig93.png "figure 9.3")
<br>**Figure 9.3:**  The opening screen for each Catalyst Town Hall meeting

**Cardano’s Treasury**

To solve the issues, a variety of treasury systems have emerged. These systems might include iterative treasury rounds when project funding requests are presented, debated, and voted on. Poor voter privacy and ballot submission security are two typical downsides. Furthermore, if master nodes are coerced, the validity of funding choices may be jeopardized, and a lack of expert input may promote undesired contributions.

Cardano was established as a third-generation blockchain to address the shortcomings of previous projects. Cardano aims to make the process more democratic by giving everyone influence and guaranteeing that choices are made fairly. It is critical to have transparent voting and financing mechanisms to achieve this. This is where Voltaire enters the picture.

The aforementioned (Lancaster University) paper on treasury systems for cryptocurrencies proposes a community-controlled, decentralized, collaborative decision-making method for long-term blockchain development and maintenance financing. This kind of collaborative intelligence is based on liquid democracy,[^23] which is a combination of direct, and representative, democracy that combines the advantages of both.

This method allows the Treasury System to use expert knowledge in the voting process while also guaranteeing that all ada holders are given a chance to vote. As a result, for each project, a voter may vote personally or delegate their voting authority to a community member who is knowledgeable about the subject.

To maintain long-term viability, the community controls the treasury system, which is regularly replenished from sources such as:

- a share of stake pool rewards and transaction costs 
- contributions or charities 
- newly minted coins held back for future financing.

The treasury will then be able to finance initiatives and pay for improvement suggestions since ada is always accumulating. As a result, the financing process may be split into ‘treasury periods,’ each of which is divided into the following phases:

- pre-voting 
- voting
- post-voting.

Project ideas may be presented at any time throughout the term, debated by experts and voters, and then voted on to finance the most critical initiatives. Despite the fact that anybody may submit a proposal, only a select few will be funded, based on a community vote.

**Decision making process**

Scientists (even nuclear physicists),[^24] developers, executive types, investors, and the general public are among the ada holders who vote. With such a diverse field of participants, with different agendas and motives, there must be proper mechanisms in place to preserve inclusivity, and ensure fair reviews and voting takes place. 

A person’s voting power is proportional to the quantity of ada they hold; the more ada they own, the more weight their vote carries. Along with direct ‘yes’ voting, a person might transfer their voting authority to an expert they trust as part of the liquid democracy concept. Note that ‘No’ voting was removed in Fund11. In this instance, the expert votes on behalf of their delegators. 

Following the vote, project ideas may be assessed and ranked depending on the number of yes/no votes; the poorest project proposals will be eliminated. The top-ranked ideas will be financed in turn until the allocated treasury money is depleted, after which the shortlisted proposals will be ranked according to their score. Breaking down the decision-making process into phases ensures each proposal is rigorously and fairly critiqued.

IOG’s research team leveraged ZK proofs to safeguard voter privacy. Zero-knowledge (ZK) approaches are mathematical methods for verifying information without exposing any underlying facts. The zero-knowledge proof in this situation indicates that someone may vote without providing any personal information other than their eligibility to vote. Any prospect of voter coercion is eliminated as a result. 

Project Catalyst is a treasury system that combines proposals, and voting processes, with the goal of fostering a democratic culture in the Cardano community. Cardano’s treasury will initially be replenished by a proportion of stake pool payouts, assuring a long-term treasury supply. Other blockchains have treasury systems, but IOG’s combines perfect anonymity thanks to zero-knowledge proofs, liquid democracy thanks to expert engagement and vote delegation (planned for Catalyst in 2024), and community participation.

It’s also worth noting that this treasury system technique may be used on blockchains other than Cardano. It has previously been suggested that it be implemented for Ethereum Classic[^25] and we’ll see later how COTI availed of the Catalyst Natives feature. 

Following a successful limited user group trial, Project Catalyst became accessible to the public. Although Cardano on-chain governance is still in its infancy, all metrics and indicators point to a bright future with the community leading the way. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig94.png "figure 9.4")
<br>**Figure 9.4:**  Catalyst overview

There are a lot of moving parts to Catalyst. This graphic from IOG’s blog post *Project Catalyst - A virtuous cycle of Cardano ecosystem development*[^26] is a good summary of the steps involved and end goals. 

## Catalyst’s early funds 

In Sept 2020, IOG announced the establishment of Project Catalyst’s first public fund, a milestone for Cardano in terms of on-chain governance, treasury, and community innovation.

The public fund was launched after five months of intensive activity across two earlier pilot funds. The first experiment, dubbed ‘Fund 0,’ was conducted with the help of an IOG focus group. Fund1 was the first time the concept was shared with the Cardano community, enlisting the aid of over 50 people to help IOG construct the platform and procedures. While this voting round did not provide ‘real’ financing, it was a significant opportunity for the IOG team and the Cardano community to test and enhance the new process.

There was a long way to go. However, with the help of the community, IOG sustained a steady rate of advancement. If Fund0 was the technical run through, then Fund1 was the dress rehearsal. Fund2, which was announced in September 2020,[^27] was the opening night when the community’s top performers fought for financing to bring their concept to fruition.

**Funding great proposals**

IOG’s pioneer group of 50 community members assisted them in identifying areas for improvement so that they could build and enhance the process before making it more broadly available. Clarifying the documentation and standards encouraged community members to participate more and submit proposals. 

To that end, IOG worked on a guide to assist anybody in creating their best proposal possible for Fund2 and beyond. The community could access up to $250k worth of ada in the first public fund. 

IOG started small, asking the community to respond to a challenge statement: ‘How can we encourage developers and entrepreneurs to create dApps and businesses on top of Cardano in the next six months?’ Funding proposals could address this with a broad range of concepts, including marketing campaigns and infrastructure development, as well as business planning and content production.

The first step was to ‘examine the problem,’ which included asking members of the community for their input. Then, through a special Telegram chat channel,[^28] IOG urged everyone to submit their ideas to the innovation platform, where they could collaborate and debate.

**The public votes**

IOG put things to a vote after the phases of brainstorming, cooperation, and proposal. Proposals were evaluated on IdeaScale, or via a mobile voting application. When it came time to vote, everyone registered using the voting app. Each participant’s ‘right’ to vote is connected to their ada holdings, and voting will earn them further ada rewards. Voting works similarly to a ‘transaction,’ enabling all participants to cast a vote to say ‘yes’ or ‘no.’ 

**How it works**

Voltaire is a critical component of the Cardano ecosystem since it enables every ada holder to participate in decision making about the platform’s future development and contribute to the ecosystem’s growth. Project Catalyst is a critical first step in achieving such capacity.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig95.png "figure 9.5")
<br>**Figure 9.5:**  Catalyst ‘here’s how it works’

Fund3 went live in January 2021, and with each fund, IOG wanted to grow the Catalyst community by encouraging more individuals to participate. Every funding round starts with a set of objectives. Each challenge symbolizes the Cardano community’s ‘intention,’ a common objective to accomplish. IOG likes to speak about ‘return on intention’ as a means of monitoring project success. Each challenge is intended to be wide enough to elicit both technical and general ideas while remaining focused. 

Fund2 had a $250,000 ada pool, while Fund3 doubled that, awarding $500,000 in ada to proposers, voters, and community advisors. The breadth, amount of money, and community participation have all increased with each funding cycle. On the IdeaScale innovation platform in Feb 2021, there were 7,000 members and 1,800 active voters. Adoption was increasing by 10% per week.

Fund4 was the most accessible and ambitious round yet, as well as the first million-dollar round — the ada pot used to finance Cardano development initiatives. The funding was used by proposal teams to create tools, construct dApps, establish developer education and training efforts, and much more. 

IOG continued to make the project more available to the Cardano community during 2021 to promote participation. Voter registration increased considerably. The redesigned registration center was now completely connected with the Daedalus wallet. Yoroi lite wallet users could easily register via a browser plugin. After that, voters could finish the process using a specific mobile voting app, which can be downloaded on iOS or Android. Project Catalyst had risen to become the world’s biggest decentralized autonomous organization (DAO) in less than six months.

## Catalyst Circle

As Fund4 came to an end in July 2021, Catalyst had already proven itself as a one-stop hub for teamwork and decentralized innovation. However, this rapid expansion brought with it new obstacles. 

Project Catalyst was gaining in contributions from increasingly different functional groups who were helping to bring the collective intelligence forward. Specifically, community advisors, funded-proposers, stake pool operators (SPOs), toolmakers & maintainers, all who contribute to Catalyst’s success and expansion.

Project Catalyst gains from having a broader set of participants as it results in more diverse ideas and proposals. It also makes communication between all of these groups more difficult. Every cohort wants to be heard, and their thoughts and concerns need to be aired at the project level.

These groups need representation and trustworthy leadership to advocate for them. Project Catalyst’s influence would be severely reduced if such representation was inadequate or non-existent. This is why the Catalyst Circle was created. Catalyst Circle[^29] was a ‘human sensor array’ that served as a representative body for all the Project Catalyst participants. The Circle kept track of Catalyst’s present state and future intentions for governance. Within the Catalyst ecosystem, it identified and discussed issues, objections, and possibilities. For example, the Circle might debate the amounts distributed to a fund, tweaks or conditions to incentive parameters, the Catalyst API, and so on.

This activity gave an insight into the hopes, desires, needs, and worries of the community inside Project Catalyst by documenting meetings and collecting activities in a backlog available to everyone.[^30] The Circle was also in charge of choosing its own future form and designing the Circle election procedures. Catalyst Circle was paused after V4. It will likely restart, or resurface in a new form, with the learnings and experiences key to any future incarnations.  

## Catalyst Natives 

As part of Project Catalyst, the first Catalyst Natives pilot was launched in late 2021. Catalyst Natives allows any project to tap into the collective intelligence of the community to solve business challenges and outsource projects. Catalyst Natives gives decentralized innovation fund management to partners, some external to Cardano, aiming to develop their ecosystem by incentivizing innovators to assist in finding solutions to problems.

**COTI, the first Catalyst Native**

Catalyst Natives expands access to Project Catalyst to organizations outside of the Cardano ecosystem could now present challenges and give incentives and rewards to individuals who successfully satisfy the challenge with their suggested innovations.

COTI presented the community[^31] with a novel technological challenge in this pilot, which was to create an innovative plug-in to be integrated with their existing ADA Pay system[^32] to support all the different e-commerce software solutions. 

Following the pilot, IOG allowed Catalyst Natives to accept more challenges from other entities; however, these challenges were selected by IOG, in the first phase, to ensure they provide value to the Cardano ecosystem. Organizations proposing challenges via Natives will finance those ideas, thus Catalyst Natives will not utilize Cardano Treasury funds to pay for the initiatives that have been successfully voted on. COTI distributed $100k in COTI tokens in Fund7, which was in addition to the $8m ada fund.

Catalyst Natives is an opportunity for businesses of all sizes to have access to a vault of ideas and the people who can help them come to life. Catalyst Natives is now aiming to assist Cardano ecosystem partners, and native asset token projects, handle particular pain points for which they either do not have the resources, or simply do not have a solution, and outsource them as Catalyst challenges for proposers to solve. 

## Later Funds



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
[^23]: Liquid democracy is a form of delegative democracy where an electorate engages in collective decision-making through direct participation and dynamic representation. This democratic system leverages parts of both direct and representative democracy.
[^24]: Cardano Network Parameters with Dr. Michael Liesenfelt | Cardano Live #54, youtube.com/watch?v=eAs_L68RO-c
[^25]: The ETC Cooperative Withdraws Support For The ETC Treasury, medium.com/etccooperative/the-etc-cooperative-withdraws-support-for-the-etc-treasury-c3f8772fff71
[^26]: Tim Richmond, ‘Project Catalyst - A virtuous cycle of Cardano ecosystem development’,  iohk.io/en/blog/posts/2022/05/10/project-catalyst-a-virtuous-cycle-of-cardano-ecosystem-development-investing-in-great-ideas-to-make-positive-real-world-changes/
[^27]: Dr Dor Garbash, ‘Project Catalyst; introducing our first public fund for Cardano community innovation’, iohk.io/en/blog/posts/2020/09/16/project-catalyst-introducing-our-first-public-fund-for-cardano-community-innovation/
[^28]: Catalyst Telegram Channel, t.me/cardanocatalyst
[^29]: Introducing the Catalyst Circle, iohk.io/en/blog/posts/2021/07/08/introducing-the-catalyst-circle
[^30]: Catalyst Circle meeting minutes, catalyst-swarm.gitbook.io/catalyst-circle/minutes
[^31]: Introducing Catalyst Natives - How any business can leverage the Cardano innovation engine, iohk.io/en/blog/posts/2021/11/10/introducing-catalyst-natives-how-any-business-can-leverage-the-cardano-innovation-engine/
[^32]: ADA Pay, adapay.finance/
[^33]:
[^34]:
[^35]:
[^36]:
[^37]:
[^38]:
[^39]:
[^40]:
