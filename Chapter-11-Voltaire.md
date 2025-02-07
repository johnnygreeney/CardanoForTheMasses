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

Every Catalyst fund cycle has provided new, remarkable accomplishments. Fund7 was no different. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig96.png "figure 9.6")
<br>**Figure 9.6:** Fund7 stats

After the votes were tabulated and counted in Fund7, 269 additional initiatives[^33] were selected to get ada. Given that each of these projects was created in response to 24 real-world problems provided by the Cardano community, as well as one additional task issued by COTI, Cardano’s first Catalyst Native pioneer, these were impressive numbers. 

This time around, over 52,500 wallets registered to vote, and community advisers reviewed over 900 proposals to assist voters make informed judgements. The number of ideas financed by the Cardano Treasury had almost quadrupled in a short period of time, reaching 575 projects. 

The Cardano Treasury now contained roughly 800m ada in order to maintain and build the ecosystem. Many of the projects that were funded in previous rounds have now been completed and their end products were being showcased.[^34]

**Fund8**

Every three months, a new Project Catalyst innovation fund campaign launches, offering the chance to obtain resources from the Cardano Treasury. Fund8 offered $16m funding in ada.

Fund8 results[^35] confirmed the momentum just keeps growing as voting turnout increased and a diverse range of projects were funded. One of the smallest amounts requested, and funded, was also one of the most significant. Sebastien Guillemot’s successful proposal[^36] meant he was the first CIP editor to be paid for his time. More editors followed, serving as stewards of the CIP process. 

Catalyst also partnered with the Financial Times and Seedstars (seedstars.com) to launch the *FT x Cardano Blockchain Challenge* where selected startups participated in a 3-day Bootcamp and connected to Seedstars’ network of mentors. 24 startups were selected to participate in a 3-month Acceleration Program.’ More details are on Seedstar’s website.[^37]

**April 21, 2019… Who pays? Who decides?** CH:[^38]

>This is why it’s so incredibly important that you have a treasury system …and voting systems because right now here’s how the cryptocurrency space works and this is why things get so toxic ….you have a very small group of people who are developers, investors, big people who are actually building stuff in the space, the entrepreneurial class, developer class the infrastructure class… then you have the speculators which are everybody else …and they hold the currency, they’re fans of it, maybe even philosophically aligned with it …but they don’t have a voice, they can’t do anything …they’re just sitting there just hoping for things to materialize.
>
>…and then a subset of them maybe move into the other class when they have smart contracts or whatever… but the vast majority of them are there yet they have opinions about where things should go…what they should do …and so the key is to give them tools to organize… tools to vote… tools to discuss the philosophy and direction …to have teeth, not just ‘here’s my opinion’, but also when my opinion is let manifest and gets a democratic consent behind it …then that opinion will turn into money …that then can be used by the other class.
>
>All of a sudden everybody has power and actually has a voice ..and an opinion and you’re not just talking about when is this coming out, or what is is it that is coming out…you’re actually talking about where do we want to go, and how are we going to get there and the things we need to do to get there… who’s the best leader to get there… you can’t fork that…. you can fork the code and have another Treasury system…but it’s like saying well that big meetup group over there… I’m going to host my own meetup group and I’m going to copy everything… the same banners and the same catering and the same everything… it doesn’t mean other people are going to show up 

## The Cardano cFund

The cFund, which was first unveiled at the 2020 Shelley summit, is an early-stage investment fund that focuses on creative firms on Cardano. Wave Financial, in collaboration with IOG, manages the cFund, a crypto-native hedge fund. The fund uses an early-stage venture approach to invest in creative technological firms that are building Cardano-based apps, services, and products, as well as other R&D projects that IOG is working on.

**The ‘c’ in cFund**

The letter ‘c’ in the name relates to the mathematics word ‘coefficient,’ which refers to a variable’s multiplier. cFund is positioned to provide a multiplier effect in terms of growth and reach for its portfolio firms by using both IOG’s and Wave Financial’s subject knowledge and industry relationships.

**Services offered**

The cFund serves as a funding provider, adviser, and partner to its portfolio firms and the greater Cardano ecosystem. cFund delivers access and direction to its portfolio by using IOG and Wave Financial resources, reputation, knowledge, and network. cFund is a great believer in adding value to its investments and strives to be the first port of call for management teams.

According to IOG’s foundational philosophy of ‘cascading disruption,[^39] most of the structures that make up global financial, governance, and social systems are inherently unstable, and slight disturbances may generate a ripple effect that radically reconfigures the system. The purpose of cFund is to find and fund solutions that bring these disparities together in a fair and transparent way for all participants. While other cryptocurrencies[^40] have strong ties to Silicon Valley, Cardano is innovating with Catalyst acting as its own ‘built in’ funding mechanism.

COTI, a decentralized and scalable payments network for the e-commerce sector, was cFund’s first investment in this area. 

Another example is Occam.Fi, a suite of DeFi solutions optimized for Cardano. Their initial product is a decentralized financing platform. The next generation of DeFi apps will be able to raise funding utilizing the Cardano blockchain thanks to this launchpad. 

**October 16, 2020. …There are a lot of different funds so could you explain to us what is DC fund, cFund and the Cardano Foundation fund?** CH:[^41]

>So, the DC fund is what we’ve termed the funds that are coming out of Catalyst… and those are grant models … Cardano doesn’t have agency, so we can’t own land, it can’t have intellectual property… it can’t have equity, these types of things …so when it gives out funding… It's like when the National science foundation (NSF) gives out funding, or DARPA[^42] gives out funding …where it’s funding the development of something because we, as a society, have determined that that is a good idea.
>
> So, for example when NSF gives research for theoretical physics …it says we, as a society, would like our brilliant physicist to be well funded so that they can figure out how time works and gravity works and so forth …but there’s no money that comes out of that …or these things but there’s a social benefit, that potentially could be leveraged over time to make the country better… Perhaps we invent anti-gravity at some point …. but it’s not the primary goal.
>
>So, we look at DC fund like that …. where we say it’s a ‘return on intention’. Grants are coming through, and the goal is to make Cardano better…. but it’s not to make Bob a millionaire, or something like that…
>
>cFund is a venture capital arm of my company and Waves[^43]… we’re working together and setting all of that up and basically that’s going to be where you run a project and you come to Charles and the others who are involved with that… you say, ‘I would like you to invest in my company… and give me the resources I need to get it to the next level…. and then we would look at you like any venture capitalist would look at you…. ask you the same questions Andreessen Horowitz (a16z.com) will ask you, or Kleiner Perkins (kleinerperkins.com) will ask you and so forth …and if we determine it’s a good investment, I’ll open up the checkbook and cut a check and send your way and we get equity back for that, because that’s a private investment.
>
>Then the Cardano Foundation they have something called the CCCI, Commercially Critical Cardano Infrastructure… and that’s saying there needs to be some product validation and bootstrapping, that Cardano really is competitive, or capable of doing the things that Ethereum and EOS and Tezos and Algorand do.
>
>So we’re going to give out some very specific very targeted grants to help get the ecosystem along …okay the DC Fund, the community is in charge of that … the grants from the (Cardano) Foundation, the Foundation’s in charge of that and they’re very directed towards catching us up and getting us where we need to go to compete with Ethereum and the rest of the gang …and the cFund is a good old-fashioned investment for things that I think we ought to have on our ecosystem.

## dReps

IOG introduced the notion of delegating your voting rights to a Delegate Representatives (dReps), and urged people interested to register during a Fund8 Project Catalyst Town Hall.[^44]  

The ongoing growth of the Cardano ecosystem is great news but, on the other hand, offers a problem. The community’s obligation to examine and vote on ideas grows as the quantity of proposals grows. A new approach was needed to guarantee that all ideas get the attention they deserve, as well as to support further development.

Ada holders may give their votes to one or more dReps through delegation. This provides the more passive voter with a chance to have their voice heard, but now across a larger number of proposals than they could read and evaluate personally.

Catalyst dReps will vote on most Project Catalyst proposals, improving the quality of decision-making within each Fund. dReps will collaborate to develop policy, gather and evaluate data, consult with experts, and ultimately vote on a variety of initiatives and issues proposed by the community. If you’d like to get involved, you can join the dRep pioneers here.[^45]  

**Fund9**

Catalyst’s relentless, Borg-like momentum continued with Fund9 opening in June 2022. There is typically something new and innovative with the arrival of each fund, and this time Cardashift[^46] joined the Catalyst Natives program.[^47] Their challenge[^48] was based on value creation through positive impact-oriented projects. Cardashift listed Cardano’s ‘green’ credentials, its focus on Africa and its deterministic nature among their reasons for partnering with Catalyst in their medium blog post.[^49] As with every quarterly fund, the rewards for successful proposals increased. The Fund9 launch guide[^50] outlined how the 16m ada was to be allocated. 

## Tactical Pause for Catalyst

Although Catalyst has been a huge success in many ways, it’s not perfect. There were also questions[^51] asked of Fund6 winner Cardax DEX after launching on Milkomeda (dcSpark’s Cardano sidechain) instead of Cardano mainchain as initially proposed. There were rumblings of discontent when one the 205 winners of Fund9 was a controversial proposal called *Daedalus Turbo*. The problem statement of the proposal read: 

>Daedalus, the decentralized Cardano wallet, is painfully slow, taking a whole day to sync initially and hours to resync when used only occasionally—an unfavorable impression of Cardano for new users. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/rick.png "Rick tweet")

Many Cardano users felt aggrieved as the sum rewarded was large, with other projects missing out. Anyone conducting a basic ‘gap analysis,’ as SPO Rick McCracken tweeted,[^52] would probably arrive at the same conclusion that the project was not timely as years of research and product development were already devoted to Mithril. For anyone following Cardano, IOG’s *Lace* (lace.io) light wallet has been prioritized over Daedalus for some time.  

From a user experience perspective, many people felt overwhelmed trying to track over a thousand proposals for a given fund on IdeaScale. Many promising projects have gone unfunded. It was generally welcomed by the community when IOG announced a ‘time out’ for Catalyst in a November 2022 blog post.[^53]

As Catalyst took a break, there was a timely SoK[^54] research paper[^55] published just around this same time, reflecting on the state of governance in ten blockchains including Bitcoin, Ethereum and Cardano.

The paper lists **seven properties** by which to assess different requirements for effective blockchain governance. 

1. **Suffrage** deals with participation eligibility, how inclusive is the governance mechanism? 
2. **Confidentiality**: are decision-makers’ inputs protected from ‘external influences’? 
3. **Verifiability**: can decision-makers confirm their input has been considered in the output?
4. **Accountability** relates to decision-makers being held accountable for their input
5. **Sustainability** questions if decision-makers are suitably incentivised?
6. **Pareto efficiency** asks ‘how well the intentions of the decision-makers can be turned into actions?’
7. **Liveness** is a measure of how quickly a blockchain’s governance mechanism can produce outputs efficiently

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig97.png "figure 9.7")
<br>**Figure 9.7:** The partition map of governance properties from the ‘SoK: Blockchain Governance’ paper

The paper concludes that while each blockchain displays some of the properties, no blockchain meets all the requirements for effective governance. It was food for thought just before the dawn of the *Age of Voltaire*. 

With the Catalyst pause after Fund9 and the *Age of Voltaire* still in its infancy, the Catalyst team introduced a new concept in the first Town Hall of 2023 called *Special Voting Events (SVE)* that leveraged Catalyst tooling. A SVE was a vote held that was unrelated to Catalyst fund cycles. It was a stopgap measure for obtaining community consent on important decisions before Catalyst resumed with Fund10 and new governance tools were being built to allow for polls and temperature checks. We learned in ScotFest 2022 presentations that Catalyst is merely a sighter for the Age of Voltaire, and 2023 would be about integrating tooling to ultimately facilitate the implementation of CIP 1694[^56] which we will discuss shortly. 

**Fund10** 

Catalyst made a welcome return with Fund10 in June 2023. The updates and changes were announced in a blog post.[^57] Catalyst’s Lead Architect, Stephen Johnson, walked through the details and demoed[^58] how the community could now start to interact with the ‘Catalyst continuous testnet’. 

Up until Fund10, Catalyst was implemented as a mix of on-chain and off-chain components. Proposals lived on IdeaScale, supported by android and iphone voting apps and a dependence on the re-purposed Jormungandr[^59] node (previously used for the Incentivized Testnet). As the Voltaire era unfolds, the voting experience has moved into the growing list of light wallets, complemented by a new website, projectcatalyst.io.

Fund10 saw 192 projects, from 100 unique proposers, receive a total of 50 million ADA in funding from the Cardano community. After the pause, deep in a bear market, ada holders were clearly hungry for Catalyst’s resumption with approximately 409,000 votes cast, a 12.48% increase compared to Fund9. 

The most significant moment of Fund10 was that it was the first time the community could decide who should be in charge of Catalyst. The community voted for IOG to continue to provide services to the community as the Catalyst Fund Operator.[^60] 

The Catalyst team’s proposal[^61] is to replace IdeaScale with ‘Catalyst Voices’. Michael Madoff, the Group Product Manager for Voltaire, joined Kriss Baird (Group Product Manager) for Town Hall #140[^62] to explain how Catalyst fits in the overall Voltaire roadmap era. Madoff explained:

>We learned a lot about experiments with Community governance through everything that's happened in Catalyst and the contributions everyone here has made

There was pushback from some proposers, for example on Twitter (X),[^63]  PACE posted: 

>This is a massive concern as IOG has a direct incentive to remove competition from categories they are competing in.

There was also an article[^64] highlighting that a very small fraction of the community has disproportionately large voting power and that up to 50% of wallet holders have virtually no influence, controlling only 1% of the voting power. 

Some suggested Quadratic Voting[^65] could address this issue, while others rejected the suggestion. Adam Rusch posted his views that *Quadratic Voting is not a silver bullet for Governance* on Cardano Forum.[^66] 

Each project team was now obliged to provide more transparency by formulating their 'Statement of Milestones,' using the Milestone Module,[^67] which monitors critical checkpoints throughout the project’s lifecycle. Projectcatalyst.io also had a full data refresh updating with all the Fund10 cohort data. This enabled users to track the progress of each funded project within the milestone program. LIDO NATION had previously blogged[^68] that “the hardest part of providing the Catalyst Explorer has been getting the data.” 

The power and reach of Catalyst hit home for me personally, when a proposal[^69] to translate this book into Japanese was approved in Fund10. Another notable funded proposal[^70] was submitted by former IOG employees, Johnny Nguyen and Dor Garbash. Their project is *‘For the community, by the community: Optimizing the ROI of Catalyst through listening to builders, expert analysis and assessment of Cardano’s Community Grants Fund. Brought to you by Catalyst and Intersect MBO Architects.’*

**Fund11**

Updates to Fund11 were announced at the Dubai Cardano Summit in November 2023. Many of the changes addressed feedback from the community. The ‘downvote’ made a welcome exit, a cap of five proposals per person was introduced and proposers could not have anything projects open from Fund7 or earlier. Fund11 also saw the birth of ‘Working Groups’. It’s not clear how they will function just yet, but will likely be something similar to what *Catalyst Circle* was. Fund11 saw the following three categories:

- Concept: for brand new ideas limited to a budget of 100K ada.
- Solution: projects who already have at least a proof of concept for review, limited to 300K ada.
- Product:  proposals with a product already in the market, limited to 750K ada.

…each category had distinct tracks to focus the scope of submissions: 

- Cardano Use Cases
- Cardano Open: Developers
- Cardano Open: Ecosystem
- Catalyst Systems Improvements: Discovery
- Catalyst System Improvements: Development

Daniel Ribar (Community and Product at Project Catalyst) talked in depth about Fund11 in a *Cardano with Paul* interview.[^71] With the longtime Catalyst leadership team now voted in for another year to run affairs, the team clarified that they will apply fund rules. Proposals submitted incorrectly, in the wrong track or out of scope, will be notified with guidance on how to come inline, otherwise they risk being withdrawn. 

There is plenty of feedback and suggestions coming from the community. For example, Santiago Carmuega, of TxPipe, explained his case[^72] for an alternative parameter that would be more effective than max number of proposals per team. Small details can have a big impact on a business model of small teams following an open-source software philosophy. Founder of *Axo*, Jarek Hirniak[^73] felt Catalyst needs to be more open to ‘bold experiments’. 

Despite its detractors, Catalyst continues to evolve and improve based on past learnings. There is a Fund11 proposal in flight to pave a way forward for different working groups.[^74] Meanwhile, Catalyst marches on with the following impressive stats at time of writing: 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig98.png "figure 9.8")
<br>**Figure 9.8:**  Project Catalyst stats Dec 14, 2023

**Participating in Catalyst**

There are several ways to participate in Project Catalyst. Submit a proposal, vote, review, comment or become a mentor. Registering an account on the collaboration platform is the first step. Another option is to join the Project Catalyst community at TownHall every Wednesday, which is live broadcast on IOG’s YouTube Channel.[^75] You can monitor each fund and catch up on previously funded proposals on projectcatalyst.io, or alternatively with LIDO NATION’s excellent Catalyst Explorer.[^76]

## The Age of Voltaire

CIP 1694[^77] was named after Voltaire’s year of birth. It is arguably the most important CIP to date as it is a proposal to bootstrap the *Age of Voltaire*. Co-authored by Charles Hoskinson, it is the first CIP he has gotten directly involved with. It’s clear a lot of thought went into it, and it’s intentionally written as a transitional, living document.

When Cardano was formed, there was a tripartite structure with Emurgo, Cardano Foundation (CF) and IOG with remits for ecosystem growth, governance and engineering respectively. It was always the intention to move to a members-based organization (MBO) that would manage the bureaucracy of protocol governance. It was hoped originally that the Swiss-based CF would be this entity but due to limitations with the stiftung[^78] structure, it was not viable. 

CIP 1694 is the fruit of years of research. IOG have been working on the idea of a decentralized update system for some time. For example, they wrote a paper *Updateable Blockchains*[^79] with the European Union, with a Horizon 2020 grant, to explore ways to implement this vision. 

Early in 2022, IOG and the CF held workshops to hammer out a way forward for the Voltaire era. The first question was ‘What is good governance?’. Charles Hoskinson explained in his ScotFest keynote that the answer was based on three different categories:

1. **The idea of representation** …did you consent to something? There is direct representation where you personally voted on something, and **delegated authority** where you hand someone else your vote. In CIP 1694, this role is called a **DRep, a delegated representative**. This concept was already introduced in a similar form in project Catalyst. IOG like to plant seeds and telegraph upcoming features. Wisdom comes from testing and experimenting with ideas in a live environment. IOG has learnt a lot from 3 years of Catalyst funding rounds. 

2. Governance needs some notion of rules, usually called a **constitution**. These are the guardrails that provide some degree of stability. The exciting thing about a constitution, in a blockchain setting, is that it can be machine understandable. Formal specifications can be the blueprints for Cardano, which a computer can understand to the extent it can integrate with an update system. Once a voting system is in place, a constitution can be ratified, hashed and embedded into a transaction. You now have the option to sign a type of ‘end user agreement’ by signing a transaction. 

3. **Institutions** are generally a target of decentralization. If we are ‘killing the middleman’, why would institutions matter? Institutions, at their best, set standards and provide a review process from domain experts. Institutions are essential for good governance as they are the custodians of knowledge and best practices. People can be biased, sometimes we need objective neutral bodies to provide guidance. After much consideration, it was decided the most important ‘anchor’ institute would be a **members-based organization (MBO)** which should operate similar to other open source initiatives like the Linux Foundation, or the Cloud Native Computing Foundation (CNCF).

**Who, or what is the MBO?**

The MBO is a point of aggregation to bring together all the different groups: over 3,000 stake pool operators, the Cardano Ambassadors, the 1,300+ projects building on Cardano, open-source projects running on Cardano (the Node, Mithril, Hydra, dcSpark, TxPipe.io, ogmios.dev, etc), IOG, CF, Emurgo, all ada holders, etc. The members will own and run the MBO, staffing the steering committees. The goal of Voltaire is to bring these moving parts together. As Charles Hoskinson stated in his keynote: “IO is not running the show, we haven't been for a long time...”

The vision for the MBO, was outlined by Johnny Nguyen (former Director of *Project Constellation* at IOG) at ScotFest:

>Serve as the aggregation point of the entire Cardano community and its members. The members-based organization aims to uncover the community's pains and desires, facilitating the development of strategies to address them, and attracting firms and individuals with a capacity and the capability to do so.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig99.png "figure 9.9")
<br>**Figure 9.9**: based on slide from ScotFest

The MBO, which would become known as *Intersect*,[^80] is the anchor institution for Voltaire, but not the only one. IOG has been steadily building out its presence in universities all over the globe, as well as opening the Hoskinson Center for Formal Mathematics,[^81] the Zero-Knowledge Lab[^82] not forgetting the Edinburgh Decentralization Index (EDI).[^83] Other institutions and MBOs will likely follow with different focuses and priorities. 

*‘Institutions… their only job is to take complexity and turn it into simplicity’* - CH[^84]

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig910.png "figure 9.10")
<br>**Figure 9.10:**  Slide from Michael Madoff’s (Voltaire Product Manager) talk at ScotFest, Note: ‘7. Info’ was later added as a ‘Proposal’

The CIP is worthy of a book in its own right, and Hoskinson has often stated he would like to write a book on governance.[^85] Like all CIPs, CIP 1694 is a living document which updates and evolves with feedback. While constitutions have been written before, we are entering uncharted waters as nothing on this scale has been attempted in the crypto space. Liquid democracy is not a new concept, but there are few examples of successful implementations. CIP 1694’s motivation is to bootstrap the Voltaire era, to integrate new and existing on-chain and off-chain components to self-govern the ecosystem. The ultimate goal is to have a governance layer on top of Cardano that is fully, end-to-end, on-chain. 

**Where we are – 5 out of 7 system**

At time of writing, governance transactions (eg. Hard forks, parameter changes, etc.) require a signature from at least five out of the seven Cardano governance (Genesis) keys, currently held by the three founding entities. This process was always intended to be an ephemeral form of governance as we got through the earlier eras of the roadmap before Voltaire. There have until now currently been two types of governance transaction:

- Protocol parameter updates using transaction field nº6 of the transaction body[^86]
- Movements of the treasury and the reserves using Move Instantaneous Rewards (MIR) certificates

**Terminology & Concepts**

The CIP introduces some new terms. First there is a **governance action** which any ada holder can submit. Three individual groups then vote to ratify, or drop, the governance action.

The three groups that form this tricameral[^87] legislative body:

- A constitutional committee, 
- DReps (same name but different role to Catalyst dReps).
- Stake pool operators (SPOs)

The **constitutional committee** will have a similar role to an upper house. Continuing the analogy, DReps would make up the lower house. **Stake Pool Operators** are the same group introduced earlier who run the nodes that power the network. A **DRep**, or **delegated representative**, can be any ada holder representing themselves, or other ada holders who have delegated their voting rights to them. 

DRep delegation will piggyback on the existing stake delegation and registration mechanisms. Just like when the ada delegated to a pool is not moved anywhere, ada delegated to a DRep is not transferred anywhere either. Also like delegated ada, you can choose to re-delegate from DRep to DRep at any time.

Ouroboros has been a huge success story, with a large majority of ada staked making Cardano one of the most decentralized networks. By leveraging the SPO network, the process gains a passionate Cardano user group who are educated and qualified to vote on crucial decisions. Registered DReps are expected to vote on governance actions regularly to still be considered active. It will be measured using a new parameter called ‘drepActivity’. Inactive DReps won’t count towards the active voting stake, but can become active again by resuming voting. 

The Cardano Constitution will be drafted with as much input from the community as possible. This Constitution will contain the guardrails, the shared values, core tenets and guiding principles agreed upon by stakeholders. In these early days, it will just be a text document with its hash recorded on-chain. IOG’s Chief Legal Officer Joel Telpner joined Charles Hoskinson for a fireside chat[^88] at ScotFest to discuss the challenges of drafting a new constitution. Telpner described what a constitution is:

> I think you can actually simplify a constitution and say it's a set of rules, but it's a set of rules to do what? It does three things. It establishes how you legislate; it establishes how you administer and establishes how you adjudicate. It creates this framework for those three functions.

Each of the three bodies plays their role in ratifying governance actions. Roles may vary for each body in different circumstances. For example, the constitutional committee will always be in one of two states, either a **normal state**, or a state of **no confidence**. As you might expect, if it's in a state of no confidence, it cannot participate in governance actions. It must be replaced before any governance actions can be enacted.

The makeup of the initial constitutional committee is not confirmed, but likely to be the core members of Intersect as well as other community members and groups. There are two ways to replace the constitutional committee. If it's in a normal state, the committee itself, along with the DReps, can both approve a motion to replace the constitutional committee. The SPOs are not required in this scenario. 

If the constitutional committee is in a state of no confidence, the SPOs and the DReps can vote to replace it. If it's already in a state of no confidence, the assumption is the majority want to replace the constitutional committee. 

The upper house generally has fewer members than the lower house, however, there is no fixed size (quorum) for the constitutional committee in CIP 1694. It can vary each time a committee is formed. The quorum size is the signature threshold, how many committee members need to sign to ratify something.

There are **seven different types of governance actions**: 

1. A motion of no confidence in the constitutional committee. 
2. Change the members (and/or quorum) of the constitutional committee. 
3. Constitution updates 
4. Hard Fork initiation
5. Protocol parameter changes
6. Treasury withdrawals (small, medium or large)
7. Information (no effect on-chain, just there for the record)

As anyone can submit a governance action, there is a **governance deposit** required to prevent spamming. This deposit is returned once the governance action is ratified, dropped or expired. Governance actions will be ratified by on-chain voting, with each of the six types of governance actions having different ratification requirements based on some, or all of the following:

- a set quorum votes of the Constitutional committee (ie. one person, one vote)
- a set stake-controlled threshold of DReps 
- a set stake-controlled threshold of SPOs

Governance actions will be checked for ratification on epoch boundaries. A vote can be a **yes**, a **no** or an **abstain**. An abstaining vote won’t count for active voting stake but if you want to change your vote, you can just vote again and it will supersede your early ‘abstain’ vote. A governance action’s progress can be monitored on-chain and is enacted one epoch after they are ratified.

There are also two pre-defined DRep options which, once selected, remain the selected response until you select otherwise:  

- If you delegate to **Abstain**, then your stake is actively marked as not participating in governance. This means your delegated stake will not be considered to be a part of the active voting stake, but it will be considered to be registered for the purpose of the incentives.
- If you delegate to **No Confidence**, then your stake is counted as a Yes vote on every ‘No Confidence’ action and a No vote on every other action. Your delegated stake will be considered part of the active voting stake and also serves as a directly auditable measure of your confidence in the constitutional committee.

The DReps will likely be the most active voters. The constitutional committee is voting most of the time, but not for a no confidence motion, or if it's a new committee or quorum vote. The upper house is typically the most powerful, while SPOs sometimes vote only if the active voting stake threshold isn't met. It might appear the SPOs have the weakest position in the tricameral body if they vote least often. However, it is more nuanced than that because the DReps and SPOs can get rid of the constitutional committee.

Also remember the SPOs demonstrated another aspect of Cardano’s decentralization when they effectively vetoed the original date for the Vasil hard fork.[^89] 

The CIP favors voting by stake over votes per person. One of the most important aspects of CIP 1694 is the notion of ‘one Lovelace, one vote’.Voting per person requires some notion of identity verification, so there is proof someone is who they claim to be. The CIP explains that a fully decentralized solution for this is currently not possible. With regulation varying by jurisdiction, it is prudent to steer clear of any mechanism that can be construed as ‘centralized’ by willfully ignorant parties. 

That said, the CIP should be open to change in future as decentralized IDs (DIDs) evolve. The World Wide Web Consortium (W3C) announced that Decentralized Identifiers (DIDs) is now an official web standard in summer 2022. IOG Chief Scientist Aggelos Kiayias also inferred they will inevitably be part of the 4th generation of blockchains.[^90] More about Decentralized Identifiers later.

**Where we are going**

The current proposal encompasses two new ledger eras. The first era will be called *Conway*, after the celebrated English mathematician John Horton Conway. The current plan for the Conway ledger era is to:

- introduce SPO voting for hard forks 
- provide an on-chain mechanism for rotating the governance keys
- rewire the ledger rules involving governance as outlined in CIP 1694

Follow the latest updates from the different engineering teams on GitHub.[^91]

If CIP 1694 is to be a success, then we should realize the vision laid out in the *Road to a Polyglot Ecosystem for Cardano* whiteboard video.[^92] The governance mechanisms outlined above would allow for multiple clients, with different dev teams, different approaches, programming languages and commercial USPs. There would be no canonical[^93] client or wallet for Cardano, just certified or uncertified. IOG have been working on this for some time, writing papers and building out expertise in formal methods, specifically with Agda.[^94]

The idea would be that interested parties, such as dcSpark, TxPipe and others, would work with *Intersect* to maintain the reference architecture. This non-production code would be put through the CIP process, before a formal spec, in Agda, is drafted. This ‘Agda core’ spec enables code extraction to serve as a reference for testing. 

There would no longer be a canonical client of Cardano, just competing clients written in Rust, Typescript, Python and Haskell. The users would just be concerned with if it was certified or not. This creates a healthy ‘survival of the fittest’ marketplace where security is assured and there is more choice for the end user. 

CH at ScotFest 2022 keynote:[^95]

>So that's Voltaire …it’s deeply philosophical, it's the hardest thing I've ever done in my life, it's the hardest thing you're ever going to do in your life and we're going to get it done, because it needs to get done and I'm damn tired of our industry failing, and it's about time we can point to something and say ‘you know what we did it the right way’. We have to tend to our own gardens first. That was a lesson of Candide. So we have to fix Cardano's governance before we have the right to complain about any other person's governance. 

Just how hard it would be became evident with some of the initial skepticism. Some felt governance was not as important as making Cardano more developer-friendly, or expediting progress on Input Endorsers, for example. Others just aren’t turned on by sitting in a room for three days hammering out the minutiae of a hypothetical vote on a parameter they’ve occasionally heard of. While many are too busy, or just not bothered to participate in governance, there is also the inevitability that topics like contingent staking would be divisive. 

The issue of contingent staking was the perfect example of how a proposed feature can be deep divisive. On the foot of the SEC crackdown on Kraken exchange, Charles Hopkinson muted the idea of contingent staking.[^96] 

This was not a new idea, it had been proposed years ago. It is the notion that stake pool operators have the option to approve ada holders who to stake with their pool. It could be implemented as a multisig transaction which could include a KYC process.

Some objectors felt that government(s) could lean on stake pool operators and force them to blacklist certain users, and that the proposed feature smacked of censorship. Others for the fear argued the new functionality would not replace existing configurations but expand the platform, extending participation to new user groups.

Hopkinson made several follow up videos[^97] in response, explaining contingent staking wouldn't replace traditional staking in any way and that both worlds can coexist. Contingent staking would not be about enforcing regulation, but enabling it.

It was an example of how every issue of governance can be subjective. How do we even measure success? Many people were interested and engaged and 2023 saw the Cardano community show up in their droves in the depths of the coldest Crypto Winter. 

So 2023 would be all about debating how to implement CIP 1694. But first people needed to be informed. Early discussions[^98] like the one between Matthias Benkort (Cardano Foundation) and Jared Corduan and Kevin Hammond (from IOG) were important to ensure there was a clear understanding of what was being proposed

The CIP was written in a deliberately high-level, approachable format to stimulate discussion and feedback. The community did not disappoint with 50 workshops, 30 in-person and 20 online, with over 1000 participants from 20+ countries.[^99] The CIP has had the most feedback (750+ comments) of any CIP with many contributors, some familiar faces, and some new ones from all corners of the globe, listed in the ‘acknowledgements’ section of the CIP.

In addition to community-led workshops, IOG, EMURGO, and the Cardano Foundation co-hosted three separate governance workshops. The CF workshop occurred in Zug, Switzerland (CF), in June, followed by Tokyo, Japan (EMURGO). The Edinburgh workshop in July marked the conclusion of the CIP 1694 design feedback loop.

Dozens of blogs have been written, and contentious issues have been argued over Reddit, Twitter (X) and Telegram. It is not possible to acknowledge every voice here, but you can dig into the finer detail by following Nicolas Cerny’s diary of events on the Cardano Forum.[^100] Some of points that stood out were:

**Consensus is rarely unanimous** 

Updates to CIP 1694 have led to wrangling among some of the community, especially the plan to incentivize participation and legitimacy by freezing the withdrawal of accrued ada staking rewards, which would be inaccessible until the wallet is delegated to a DRep. While many felt DReps should be rewarded, or at least comped, for their work, others argued that there should be no incentives for DReps to do their job, as it might attract the wrong sort only ‘in it for the money’. The interim proposal is to escrow Lovelace from the treasury until a way forward can be agreed, likely using the on-chain governance mechanism currently under construction. 

Alternative governance mechanisms have been put forward. @HeptaSean shared his *Minimal Viable Governance* proposal on the Cardano Forum.[^101] He suggests a leaner governance framework without a constitution or CC, no DReps, no SPO votes where every ada holder can directly vote.

There is also Cardano Problem Statement, CPS-0007,[^102] submitted by Pi Lanningham. The CPS aims ‘to frame a set of motivations, goals, constraints, and open questions for the very broad topic of Cardano governance’ to stimulate a wider discussion on whether there is a viable alternative to CIP 1694. Another useful contribution was CPS–0006 *Governance Security*[^103] from Rick McCracken who also ran several community governance workshop sessions.[^104] 

In May, the Cardano Foundation conducted a SPO on-chain poll,[^105] a new mechanism (defined in CIP-94)[^106] to allow stake pool operators to vote on crucial issues based on the stake delegated to their pool. The poll is similar to governance action 7 (info) as neither have a binding effect although ‘minPoolCost’ was subsequently cut to 170 ada.

The inaugural poll asked ‘Which setup would you prefer to be put in place from Q3 2023 onwards?’ with 6 options:

- Keep k at 500 and minPoolCost at 340 ada.
- Keep k at 500 and halve minPoolCost to 170 ada.
- Increase k to 1000 and keep minPoolCost at 340 ada.
- Increase k to 1000 and halve minPoolCost to 170 ada.
- I would prefer to abstain.
- None of the above.

Not everyone approved of the options in the poll. Some found it strange that there was no ‘MinPoolCost = 0’ option, while others felt the question lacked context. With this feedback in mind, there were discussion threads created on the Cardano Forum[^107] to explore the options in more detail.

In an essay titled *Cardano Improvement Proposal — 1694: Can Decentralized Communities Make Superior Decisions?*[^108] authors Kenric Nelson, Juana Attieh, Megan Hess, Vanessa Cardui, and Stephen Whitenstall evaluated Cardano’s shift to a community-led governance model. The recurring issue of unfair distribution of voting power reared its head again. The essay warns a system with a one-coin-one-vote (1c1v) philosophy can result in a plutocracy,[^109] with a small portion of addresses tend to control a disproportionate amount of voting influence. 

Governance on Cardano hit a milestone on Friday, June 30, 2023 when the CIP 1694 Pull Request was merged into the main branch of the Cardano Foundation CIP repository. The proposal’s status advanced on to the ‘Proposed’ stage. The update was not unanimously welcomed with some contributors concerned[^110] things were being rushed without other alternative models being explored sufficiently. Veteran CIP editor Matthias Benkort explained the reasoning for the merge:

>It has arguably undergone sufficient conversations, the specification is well articulated and the rationale pretty furnished as well. Originally, we wanted to wait for after the final Edinburgh workshop, though with @JaredCorduan no longer able to continue championing the pull request, it is better to continue conversations on this CIP in separate pull requests. It should also help make conversations a bit more manageable as they can be scoped to specific areas of the CIP. (…)  I'd like to remind everyone about the goals of the CIP process and what the process itself stands for. A CIP is NOT binding anyhow, nor is it any kind of authoritative document that command changes on a project. A CIP is first and foremost, a technical solution to a problem that is thoroughly discussed and backed by arguments.

In any case, SPOs have the final say as they must upgrade their nodes with any proposed changes. 

The Edinburgh meetup in July was the capstone workshop for all the CIP 1694 feedback to date. Representatives from the in-person workshops held around the world were invited to discuss and share their insights with their peers. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig911.png "figure 9.11")
<br>**Figure 9.11:** Screenshot from the Miro board[^111] set up for the Edinburgh CIP 1694 workshop

In a presentation, Kevin Hammond listed six key issues which came up in all workshops: on-chain deposits, treasury withdrawals, community tooling, action expiration, action thresholds, and DRep incentives. There was broad consensus on most topics but some required a specialized working group to map a way forward. You can follow some of the discussions on the public Miro board.

As almost everything in Cardano takes the form of a transaction, getting the metadata standard correct is critical. Metadata allows developers to embed information specific to the context of the transaction. For example, the NFT standard (see CIP-25, CIP-68, CIP-60) on Cardano has evolved with new capabilities unlocked with past roadmap releases. Pi Lanningham authored CIP-0100[^112] to clear up what metadata standards need to be introduced to enable the on-chain governance mechanisms proposed in CIP 1694.  

CIP-95[^113] is a crucial CIP, which extends CIP-30 and describes the interface between webpage/web-based stacks and Cardano wallets. More specifically, it is a specification (based on the Draft Conway Ledger Era) that defines the API of the javascript object that is injected into web applications. The CIP enables voting capabilities for governance tools. At the Edinburgh hackathon, decisions were made around open questions[^114] and the base design was approved. 

We’ve only scratched the surface. As governance can be subjective, it's best you read CIP 1694 yourself, especially the *Rationale* and *Changelog* sections which add context. 

**Cardano Ballot**

In November, Intersect announced[^115] a community-wide poll to get a ‘temperature check’ on CIP 1694’s progress. The vote took place on the Cardano Ballot app developed by the Cardano Foundation which had been stress-tested on the Cardan Summit Awards 2022 and 2023. The Cardano Ballot is powered by the open-source *Wallet Connector*[^116] developed by the Cardano Foundation, based on the CIP-30 and CIP-8 standards. It works with many Cardano wallets but hardware wallets were not supported due to features missing in the firmware of the hardware wallets. Vacuumlabs are working on a solution, funded by Catalyst Fund 10.[^117] IOG engineers also contributed to the ballot event which posed the question: 

>Based on the current progress, should we as a Cardano community continue to develop and deploy minimum viable on-chain governance as described in CIP 1694, subject to the final approval of the SPOs?

Participants voted Yes, No, or Abstain and could also include a comment with their vote. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig912.png "figure 9.12")
<br>**Figure 9.12:** Screenshot from 1694ballot.cardano.org/vote

The poll was non-binding and part of a broader iterative process to garner community participation and feedback. As usual, the community’s response was emphatic. Many felt it would not be a fair reflection of community sentiment as most people hold their ada on hardware wallets. Others questioned why existing community tooling was not used. There was some confusion over the abruptness of this poll suddenly appearing on their timeline, although it had been muted as far back as the NFTxLV in September and featured on the Intersect Roadmap.[^118]

Undeterred, the community found a workaround. *Summon Platform and DripDropz* collaborated to offer an alternative CIP 1694 temperature check.[^119] The poll itself remained unchanged but people could now vote with hardware wallets and also review live results. The drama from the initial ‘Twitter storm’ was short lived and the ballot(s) only served to demonstrate decentralized governance in practice. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig913.png "figure 9.13")
<br>**Figure 9.13:** Temperature check results

Nicolas Cerny followed up with some forensic analysis.[^120] He noted some of the possible reasons for the low turnout may have been the nature of the poll being non-binding, the relatively short notice of two weeks for the Cardano Ballot event, and many ada holders are just not interested in participating in the governance process. It will hopefully serve as a learning experience and the subsequent open-sourcing of the Cardano Ballot code[^121] means anyone can now initiate their own poll, encouraging more engagement and participation in future.

## Intersect

The much talked about MBO was renamed *Intersect*, as in the intersection of Cardano and its community, and launched in July after the Edinburgh workshop. Intersect is an aggregation point for Cardano’s community governance and development. It is ‘an MBO’, not ‘the MBO’...other MBOs will likely follow.  

*Intersect* will serve as a steward of the underlying blueprints so this means the code for the Cardano Node, core Cardano libraries and components moving over from IOG’s GitHub repos to Intersect repos. It will be the community’s town hall for advancing Cardano’s roadmap. Grants and work packages[^122] will be available for members to apply for.  CH:[^123]

>..there is an open question of what is the next priority? So Intersect is one of the organs, not the only one, but an organ where that is discussed from a product to product viewpoint. And the people who serve in those working groups are basically going to be the ones who start filling out that product priority…and the engineers are the ones who go and execute that, but they execute at the behest of the backlog.
>
>…
The other thing is it helps us with business intelligence, where we, for the first time ever as an ecosystem, really need to look at other ecosystems. I've been trying to do this, like with Sean Ford[^124] coming in from Algorand, and you know Eran (Barak) and others coming in from the Polkadot ecosystem. But it turns out that other ecosystems do great work too, and they think differently and sometimes value things differently, but a lot of that stuff from those other ecosystems could be of tremendous benefit to Cardano… but it has to be harnessed, translated and captured in the right way. So when you have a bucket like Intersect what that allows you to do is to not only have Cardno community members but within those working groups you could have people from other ecosystems.

There already exist several institutions where community members share their expertise to support a specific need or aspect of Cardano. There is the Cardano DeFi Alliance (CDA)[^125] which standardizes best practices within the DeFi ecosystem. The NFT Guild[^126]  which focuses on developing standards and tooling for the Cardano NFT space. The UTXO Alliance[^127] advocates interoperability across systems using UTXO-based blockchains. 
Members from these existing groups will amalgamate into the various Intersect boards, councils, committees and working groups. The goals of Intersect are distilled in it’s five pillars:

1. Support the **community** to develop the ecosystem by hosting developer-focused conferences, hackathons, and events.
2. Administrate and champion Cardano’s **community-led governance** implemented by CIP 1694.
3. Coordinate delivery of the community approved **Cardano Technical Roadmap**.
4. Coordinate the routine **maintenance** of Cardano for system stability.
5. Coordinate open source **development** of core technologies for Cardano.

**Intersect Committees** 

The Parameters Committee meets every few weeks to review Cardano's parameters encompassing network, technical and economic parameters. The minutes of these meetings are available on the Cardano Forum.[^128] You can see the consideration that goes into a parameter change by reading Matthew Capps *Protocol Change Proposal-001, Chronology of Documented Events* tweet.[^129]

An important stream for Intersect is the Cardano Civics Committee (CCC) which is an advisory committee focussing on off-chain discussions about governance proposals. It will support the Constitutional Committee and monitor the governance process to ensure it is working as intended. Notable members include Adam Rusch[^130] who holds a PhD in Social Sciences and Marcus Fysh, British Member of Parliament for Yeovil.

The Membership, and Community Committee (MCC) fosters community inclusivity. More committees and working groups will follow in 2024… - Amar Singh, EMURGO[^131]

>...it's not decentralized governance if it's not by the people, for the people, run by the people...


Key to Intersect being a success is the commitment to open-source development on Cardano. The Open Source Committee (OSC) is the shepherd for this open-source approach. Without wanting to get lost in abbreviations, the OSC will act as an advisory body to the Open Source Program Office within Intersect. The OSC has mapped out the following tenets:

- Maintain the **legitimacy** of the Cardano Open Source Project (COSP)
- Maintain the (high quality) security and health of the Cardano mainnet
- Sustainable Development of the COSP must continue.
- Be a good Open Source citizen.

Pat Sheridan, co-founder and CEO of Modus Create, is the interim Chair for the crucial bootstrapping phase. Michael Peyton Jones created a first draft[^132] of the open source governance policy. The committee is always open to new members. To learn more, it’s best to check out the Intersect discord[^133] #OSC-feedback channel for the latest news.

True open source means having flexibility to choose from different options. The Cardano Foundation has also been following an Open Source strategy. Director of Product, Alex Apeldoorn, outlined the suite of products[^134] released in 2023. Ledger Sync,[^135] Identity Wallet,[^136] Cardano Explorer,[^137] Aiken,[^138] Kupo,[^139] and Ogmios[^140] all follow open source principles and make life easier to develop on Cardano. 

We already focussed on Aiken’s growing adoption. Acknowledging that Java is still the preferred language for a lot of enterprise developers, the CF created Ledger Sync and the Identity Wallet in Java as open source tools with this audience in mind. Ledger Sync puts sequential blockchain data in a new, more accessible database structure, while the Identity Wallet is a W3C-compatible mobile wallet for managing self-sovereign identities across Cardano and other blockchains. The wallet supports multiple standards, integrating key event receipt infrastructure (KERI) for interoperability so as to fit a broad range of use cases and enterprise adoption.

But wait, there’s more… The *Cardano Ballot* project, a Fully functional Merkle Tree in Java / Aiken,[^141] the Cardano Conversions library[^142] and State Channels L2 (hydra-java Client)[^143] were all open-sourced. Not forgetting what we mentioned early about the CF open sourced the rewards calculation,[^144] in an effort to enable anyone to perform and validate the rewards calculation in a way that is independent of a single implementation. 

With a strong finish to the year, with multiple launches in December, the CF is poised to build on this momentum in 2024. As CF engineer Mateusz Czeladka remarked,[^145] *‘Open Source has a compounding effect, others can build on what you created. Love it’*

## SanchoNet 

There are a lot of tools to be built in order for CIP 1694 to become a reality. We naturally need a testbed for this journey. Also to come out of the Edinburgh meetup in July ‘23 was *SanchoNet*,[^146] a testnet for people to try out new tools and mechanisms related to CIP 1694.  

SanchoNet was named after the character Sancho Panza, Don Quixote’s companion in Miguel de Cervantes’ literary classic. SanchoNet is ultimately about transforming an aspirational digital *Barataria*[^147] into on-chain governance reality on Cardano mainnet. Note SanchoNet is not another (ITN) incentivized testnet but a testnet where test-ada is used to stress test experimental features. 

First introduced to the community in Edinburgh, SanchoNet was rolled out in 6 phases with each Cardano Node (cardano-cli) release enabling new governance capabilities. As it’s fast moving and it’s best to check for the latest updates on IOG’s Discord server in the dedicated SanchoNet channel.[^148]

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig914.png "figure 9.14")
<br>**Figure 9.14**: SanchoNet roadmap

Although limited to stake pool operators at the command line initially, the next phase started once the tools were in place for DRep to register, receive delegation and vote. Test-ada holders could also now participate by submitting governance actions. There are plenty of areas where developers can contribute, with tooling required for wallet integrations, DRep explorers to visualize blockchain data, governance dashboards, etc. SanchoNet follows its own independent development roadmap scoped with a technical, rather than governance focus.  

The community stepped up as it always does. Mike Hornan,[^149] SPO of ‘able’ stake pool, led the way contributing cardano-cli cheat sheets, infographics, hosting workshops and recording YouTube tutorials.[^150] Adam Dean[^151] maintained the testnet, Blockfrost[^152] provided API access to SanchoNet. CIP editor Ryan Williams[^153] hosted biweekly ‘sancho-wallets’ open hours on Discord to discuss SanchoNet news and CIP-95 progress. Emurgo released a Serialization Library[^154] for the Conway ledger era. The library[^155] can be used to generate new certificates and transactions that can be submitted to SanchoNet. Many others contributed with dozens of SPOs signed up running the SanchoNet network. Although there are different roadmap eras and separate engineering streams, almost everything overlaps in Cardano and so it’s no surprise the Mithril team have been busy testing on SanchoNet also.[^156]

**GovTool**

GovTool was first demoed at September's NFTxLV event[^157] and is available for testing at sanchogov.tools. As this is new tool and process for most users, there is comprehensive documentation including a testing ‘to do’ list.[^158] Governance tooling follows an open source model in that it is owned and maintained by the community. Intersect committees and working groups hosting and maintaining tooling.

You can still use the cardano-cli if you prefer, but now there is also the user-friendly GovTool UI which allows a broader base of ada holders to test governance features available in SanchoNet. 

We are currently deep in the weeds of Phase 5, with the focus on more technical functionality testing and building network resilience. Ada holders could now propose and endorse parameter updates. The final Phase 6 will focus on the governance actions related to hard fork initiation. 

If 2023 was the year we talked about governance, 2024 will be about implementation. The consultation period for the constitution will come into focus, guided by the Cardano Civics Committee (CCC). Then there is the milestone that will be the Chang hard fork. The Constitutional Convention is set for late 2024 in Buenos Aires, Argentina which will capture the feedback from the Constitution Global Workshop Series. The year will climax with the ‘moment of truth’ when an on-chain vote to ratify the constitution will take place. CH at 2023 Dubai Summit[^159]

>Currently Catalyst is the only mechanism upon which we access the cardano treasury…well that's great, but that's like saying you have a garden hose to access your water from the tank… it's very small throughput, there's a lot of water in the tank ... the Cardano treasury has a lot of funds in it, but not a lot of it gets emitted out …and that was by design, because we had to wait for a governance system to be in place. Now that there's a governance system in place, technically speaking CIP 1694 would allow the community to open up the treasury for things that aren't related to Catalyst.
>
>So in practice you'd have to treat it like a government… and what a government does, they have budget …little pie chart right you have slices in the pie …you have your slice for development, and your slice for marketing, and your slice for bureaucracy, and you know your slice for you know buying an island somewhere… or whatever the hell you guys want to do….but you have to draw the pie …and you have to decide how big of a pie is that going to be? Is it $50 million? Is it $100 million? So one of the biggest governance challenges actually next year is going to be how do we, as a community, come together, and decide on an annual budget for how much resource funds should be actually spent out of the Cardano treasury?  

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
[^33]: Fund 7 initiatives, drive.google.com/file/d/193GZulHuk0zhpTrMiLhcNC4OeEMoRyIa/view
[^34]: Project Catalyst - Funded Projects Reporting (public MVP), docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/edit#gid=416498551
[^35]: Fund 8 results, drive.google.com/file/d/1s3jCE7pmoUujy3ASMia-UhFl2KLi_hnf/view
[^36]: CIP Editor funded, twitter.com/SebastienGllmt/status/1525139808926191618
[^37]: ‘FT x Cardano Blockchain Challenge’, seedstars.com/community/entrepreneurs/programs/ft-cardano-blockchain-challenge/
[^38]: Post Conference recap, thoughts and an AMA 04/21/2019, youtu.be/pBXZVrBQ6U8?t=5003
[^39]: Cardano | The First Domino, youtube.com/watch?v=W7gGO058rtU
[^40]: Crypto Startup Solana Raises $314 Million to Develop Faster Blockchain, wsj.com/articles/crypto-startup-solana-raises-314-million-to-develop-faster-blockchain-11623240001
[^41]: Entrevista CEO IOG Charles Hoskinson e Maria Carmo #Cardano #ada Delegue na CARDs ou @cardanistas, youtu.be/rHu6oLTZ7kI?t=3061
[^42]: DARPA: The Defense Advanced Research Projects Agency is a research and development agency of the United States Department of Defense responsible for the development of emerging technologies for use by the military
[^43]: Waves, everipedia.org/wiki/lang_en/waves-cryptocurrency
[^44]: Project Catalyst Fund8 launch - Town Hall #1 February 2022, youtube.com/watch?v=rNZJvzjgduM
[^45]: Catalyst dRep applications, bit.ly/3rSyHvP
[^46]: Cardashift is a community-run launchpad that raises funds, builds and accelerates startups that are solving social and environmental issues.
[^47]: Fernando Sanchez, ‘Introducing Catalyst Natives - How any business can leverage the Cardano innovation engine’, iohk.io/en/blog/posts/2021/11/10/introducing-catalyst-natives-how-any-business-can-leverage-the-cardano-innovation-engine
[^48]: Fund9 Catalyst Natives Cardashift challenge: demonstrating and monetizing impact, iohk.io/en/blog/posts/2022/06/01/fund9-catalyst-natives-cardashift-challenge-demonstrating-and-monetizing-impact/
[^49]: The 3 reasons why we choose Cardano to maximize our impact, cardashift.medium.com/the-3-reasons-why-we-choose-cardano-to-maximize-our-impact-28b2e914e894
[^50]: Fund9 launch guide, drive.google.com/file/d/1kJ8F6doXUIJQRiA5pmSMxXc9feVfF21y/view
[^51]: @cwpaulm questions CardaxDEX, twitter.com/cwpaulm/status/1597666144059432960?s=20&t=HBr5f_ZkSoMQ4rzv0eIdOA
[^52]: Daedalus Turbo gap analysis, twitter.com/RichardMcCrackn/status/1575057817181966337?s=20&t=XXfR1C0qB9jx6InYxgpQEA
[^53]: Repositioning Project Catalyst ahead of the next funding round, iohk.io/en/blog/posts/2022/11/01/repositioning-project-catalyst-ahead-of-the-next-funding-round/
[^54]: Systemization of Knowledge (SoK) papers evaluate, systematize, and contextualize existing knowledge.
[^55]: Kiayias, Lazos (2022), 'SoK: Blockchain Governance', arxiv.org/pdf/2201.07188.pdf
[^56]: CIP 1694, github.com/cardano-foundation/CIPs/tree/master/CIP 1694
[^57]: Co-building the gears of innovation through the relaunch of Project Catalyst with Fund10, projectcatalyst.io/blog/co-building-the-gears-of-innovation-through-the-relaunch-of-project-catalyst-with-fund10
[^58]: Project Catalyst - Weekly Town Hall - #128, youtu.be/CaKQAhnOKbE?t=1819
[^59]: Jormungandr Node, github.com/input-output-hk/jormungandr/blob/master/CHANGELOG.md
[^60]: Project Catalyst Fund10 proposals: forging the road ahead, together, projectcatalyst.io/blog/project-catalyst-fund10-proposals-forging-the-road-ahead-together
[^61]: IOG Catalyst Team : Ideascale replacement and web-browser based Voting Centre with liquid democracy aka “Catalyst Voices”, .lidonation.com/en/proposals/iog-catalyst-team-ideascale-replacement-and-web-browser-based-voting-centre-with-liquid-democracy-aka-catalyst-voices-f10
[^62]: Project Catalyst - Weekly Town Hall - #140, youtube.com/watch?v=2f7v0x6xal0&t=2548s
[^63]: Cardanopace on X, twitter.com/cardanopace/status/1694373619961393534?s=20
[^64]: Cardano Project Catalyst: Dissecting the Imbalance in Voting Power, thecryptobasic.com/2023/09/05/cardano-project-catalyst-dissecting-the-imbalance-in-voting-power/
[^65]: Quadratic voting is a collective decision-making procedure which involves individuals allocating votes to express the degree of their preferences, rather than just the direction of their preferences.
[^66]: Quadratic Voting is not a silver bullet for Governance, forum.cardano.org/t/quadratic-voting-is-not-a-silver-bullet-for-governance/116135
[^67]: Project Catalyst Milestone Module, milestones.projectcatalyst.io/
[^68]: ‘From Prototype to Powerhouse: Catalyst Explorer in Fund 10 and beyond’, lidonation.com/en/posts/from-prototype-to-powerhouse-catalyst-explorer-in-fund-10-and-beyond
[^69]: ‘Cardano For the M₳sses - Japanese Book’, lidonation.com/en/proposals/cardano-for-the-marasses-japanese-book-f10
[^70]: Johnny Nguyen and Dor Garbash Fund10 proposal, lidonation.com/de/proposals/for-the-community-by-the-community-optimizing-the-roi-of-catalyst-through-listening-to-builders-expert-analysis-and-assessment-of-cardanos-community-g-f10
[^71]: Cardano Catalyst Fund 11 is Now Open With Big Changes From Fund 10, youtu.be/7hKZWYC7YHQ?si=KrShWlibgtAoG5wX
[^72]: @santicarmuega on Fund11 changes, twitter.com/santicarmuega/status/1730977552519270712?s=46
[^73]: @ravanave views on Catalyst, twitter.com/ravanave/status/1730363424796737649?s=46
[^74]: Catalyst Working Groups Research & Scoping Analysis by IOG Catalyst Team, Rare Evo, and Sustainable ADA, cardano.ideascale.com/c/idea/113181
[^75]: IOHK youtube channel, youtube.com/c/IohkIo
[^76]: LIDO NATION Catalyst Explorer, lidonation.com/en/catalyst-explorer
[^77]: CIP 1694, github.com/cardano-foundation/CIPs/tree/master/CIP 1694
[^78]: A stiftung is a foundation which exists to give effect to the stated, non-commercial wishes of its founder, as set out in a foundation deed and the articles of association (statutes).
[^79]:  Ciampi, Karayannidis, Kiayias and Zindros (2020), 'Updatable Blockchains', iohk.io/en/research/library/papers/updatable-blockchains/
[^80]: Intersect ‘Uniting the Cardano Ecosystem’, intersectmbo.org
[^81]: Carnegie Mellon Receives $20 Million to Establish Hoskinson Center for Formal Mathematics, cmu.edu/news/stories/archives/2021/september/hoskinson-center-for-formal-mathematics.html
[^82]: Cardano builder IOG and University of Edinburgh launch Zero-Knowledge Lab to drive greater blockchain scalability and security, iohk.io/en/blog/posts/2022/11/18/cardano-builder-iog-and-university-of-edinburgh-launch-zero-knowledge-lab-to-drive-greater-blockchain-scalability-and-security/ 
[^83]: Cardano builder IOG and University of Edinburgh to create first ever index to provide industry standard metric for crypto decentralization, iohk.io/en/blog/posts/2022/11/18/cardano-builder-iog-and-university-of-edinburgh-to-create-first-ever-index-to-provide-industry-standard-metric-for-crypto-decentralization/ 
[^84]: Charles Hoskinson: Crypto regulations & policy, Importance of stablecoins & the future of Cardano, youtu.be/uEV8tQ6z87k?si=iVazdagl5JWZez3q&t=1983 
[^85]: Charles Hoskinson - Book about Decentralized Governance, youtube.com/watch?v=kutZ41J-tTU 
[^86]: github.com/input-output-hk/cardano-ledger/blob/8884d921c8c3c6e216a659fca46caf729282058b/eras/babbage/test-suite/cddl-files/babbage.cddl#L56 
[^87]: Tricameralism is the practice of having three legislative or parliamentary chambers. It is contrasted with unicameralism and bicameralism, each of which is far more common 
[^88]: ScotFest fireside chat with Joel Telpner, youtube.com/watch?v=YvTfSx6pv9Y 
[^89]: @KtorZ ‘delay is good’, twitter.com/_KtorZ_/status/1538101313564811265?s=20&t=Kygsq-InxS6AO0XhjFfr8g 
[^90]: First Principles: Research for the Future, youtu.be/MVuweooiXPI?t=2280 
[^91]: Ledger team updates, input-output-hk.github.io/cardano-updates/2023-01-19-ledger 
[^92]: Road to a Polyglot Ecosystem for Cardano, youtube.com/watch?v=skcCg1WaedA 
[^93]: Canonical, in computer science, is the standard state or behavior of an attribute. This term is borrowed from mathematics, where it is used to refer to concepts that are unique and/or natural. 
[^94]: Agda is a dependently typed functional programming language. Charles Hoskinson referred to it as 'Super Haskell' 
[^95]: IO ScotFest Keynote with Charles Hoskinson, youtu.be/tbtkClr3Y3I 
[^96]: Staking and Regulation, youtube.com/live/J7y2tvpHY5w?feature=share&t=412 
[^97]: Contingent Staking (Part 2), youtube.com/watch?v=C_a9F0aSUSk
[^98]: CIP 1694: An explainer, youtube.com/watch?v=obFeC2JS_IQ&t=5s
[^99]: Interactive map of 1694 workshops, cip1694.intersectmbo.org/
[^100]: Cardano Governance Updates: Community Input, Voltaire Phase, and CIP 1694 Updates, forum.cardano.org/t/cardano-governance-updates-community-input-voltaire-phase-and-CIP 1694-updates/115878
[^101]: Minimal Viable Governance, forum.cardano.org/t/minimal-viable-governance/115621
[^102]: CPS 0007 - Volaire Era Governance, github.com/cardano-foundation/CIPs/pull/481
[^103]: CPS 0006 - Governance Security, github.com/cardano-foundation/CIPs/pull/491
[^104]: Governance Security Workshops, twitter.com/RichardMcCrackn/status/1650135262574395392?s=20
[^105]: Entering Voltaire: on-chain poll for SPOs, cardanofoundation.org/en/news/entering-voltaire-on-chain-poll-for-spos/
[^106]: CIP-0094? | SPO On-chain Polls #496, github.com/cardano-foundation/CIPs/pull/496
[^107]: Cardano Forum SPO-Poll threads, forum.cardano.org/tag/spo-poll
[^108]: Cardano Improvement Proposal - 1694: Can Decentralized Communities Make Superior Decisions?, medium.com/@photrek/cardano-improvement-proposal-1694-ca971194eb20
[^109]: A plutocracy is a state or society governed by the wealthy
[^110]: Reaction to CIP 1694 status update, github.com/cardano-foundation/CIPs/pull/380#issuecomment-1615285365
[^111]: Edinburgh CIP 1694 workshop Miro Board, miro.com/app/board/uXjVM7H7URo=/
[^112]: CIP-0100? | Governance Metadata, github.com/cardano-foundation/CIPs/pull/556
[^113]: CIP-95, cips.cardano.org/cip/CIP-0095
[^114]: CIP-95, github.com/Ryun1/CIPs/blob/governance-wallet-connector/CIP-0095/README.md#open-questions
[^115]: Cardano Ballot Event on CIP 1694, intersectmbo.org/news/intersect-announces-cardano-ballot-on-future-governance
[^116]: Cardano Foundation Wallet Connector, github.com/cardano-foundation/cardano-connect-with-wallet
[^117]: Vacuumlabs Fund10 Proposal, milestones.projectcatalyst.io/projects/1000108
[^118]: Intersect Roadmap, intersectmbo.org/roadmap
[^119]: Summon Platform Poll, tempcheck.smmn.app/poll
[^120]: Voltaire Update: The CIP-1694 Temperature Checks - Insights and Analysis, forum.cardano.org/t/cardano-governance-updates-community-input-voltaire-phase-and-cip-1694-updates/115878/18#voltaire-update-the-cip-1694-temperature-checks-insights-and-analysis-1
[^121]: Cardano Ballot, github.com/cardano-foundation/cf-cardano-ballot
[^122]: A ‘work package’ is like a procurement brief capturing the requirements that need vendor support to deliver. 
[^123]: Latest Cardano and Crypto Developments with Charles Hoskinson, 14 Dec 2023, twitter.com/i/spaces/1YqxoDPoMdaKv
[^124]: IOG appoints W. Sean Ford as CEO of newly created stablecoin venture, iohk.io/en/blog/posts/2023/10/23/iog-appoints-w-sean-ford-as-ceo-of-newly-created-stablecoin-venture/
[^125]: Cardano DeFi Alliance, cardanodefialliance.org/
[^126]: NFT Guild, nft-guild.io/
[^127]: UTXO Alliance, utxo-alliance.org/
[^128]: Parameters Committee Updates, forum.cardano.org/c/governance/parameters-committee-updates/220
[^129]: Matthew Capps, Protocol Change Proposal-001 tweet,  twitter.com/cryptstitution/status/1725745468821344432?s=46
[^130]: Adam Rusch, twitter.com/AdamRusch
[^131]: Transparency for Governance, youtu.be/a1DoWRyMVw4?si=FDRObWts8x56xnbR&t=152
[^132]: Initial draft of governance policy, github.com/IntersectMBO/community/pull/1
[^133]: Intersect discord server, discord.com/invite/Gr7FhzaVrk
[^134]: Cardano Foundation 2023 Products to Advance Blockchain, cardanofoundation.org/en/news/cardano-foundation-2023-products-to-advance-blockchain/
[^135]: Ledger Synch, cardanofoundation.org/en/news/accessing-cardano-blockchain-data-with-ledger-sync/
[^136]: Identity wallet, identity.cardanofoundation.org/
[^137]: Cardano Explorer, beta.explorer.cardano.org/en/
[^138]: Aiken, cardanofoundation.org/en/news/aiken-the-future-of-smart-contracts/
[^139]: Kupo, github.com/CardanoSolutions/kupo#readme
[^140]: Ogmios, ogmios.dev/
[^141]: Merkle Tree implementation in Java / Aiken, github.com/cardano-foundation/merkle-tree-java
[^142]: Cardano Conversions Utility, github.com/cardano-foundation/cf-cardano-conversions-java
[^143]: hydra-java, github.com/cardano-foundation/hydra-java
[^144]: Releasing an open source rewards calculation, cardanofoundation.org/en/news/releasing-an-open-source-rewards-calculation/
[^145]: Mateusz Czeladka post, linkedin.com/posts/mateuszszczap_github-cardano-foundationcf-cardano-ballot-activity-7138582045655568385-K6gY/ 
[^146]: SanchoNet, sancho.network/
[^147]: Barataria was a fictional island awarded to Sancho Panza as a prank in Part II of Cervantes' novel Don Quixote
[^148]: SanchoNet discord channel, discord.com/channels/826816523368005654/1128361520514994178
[^149]: Mike Hornan, twitter.com/Hornan7
[^150]: Mike Hornan SanchoNet tutorials, youtube.com/@hancoeur/videos
[^151]: Adam Dean, twitter.com/adamKDean
[^152]: Blockfrost, twitter.com/blockfrost_io
[^153]: Ryan Williams, github.com/Ryun1
[^154]: Serialization converts the state of an object into a byte stream. Deserialization is the reverse process.
[^155]: Emurgo Cardano Serialization Library, github.com/Emurgo/cardano-serialization-lib
[^156]: Mithril on SanchoNet, github.com/input-output-hk/mithril/issues/1173
[^157]: NFTxLV, nftxlv.com/
[^158]: GovTool documentation, docs.sanchogov.tools/about/sancho-govtool-testing
[^159]: Closing Keynote- Looking Ahead to 2024 and Beyond, youtu.be/OzLdZxkfAeQ?si=hmL23uC9u8dCVBnT&t=846
