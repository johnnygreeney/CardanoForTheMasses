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



**_The rest of the chapter will be uploaded soon..._**




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
[^78]:
[^79]:
[^80]:
