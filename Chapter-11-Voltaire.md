# Chapter 11: Voltaire

*‘No problem can withstand the assault of sustained thinking’* ― Voltaire

### to do: add markdown format

Age of Voltaire

CIP-1694

CIP-1694 was named after Voltaire’s year of birth. It is arguably the most important CIP to date as it is a proposal to bootstrap the age of Voltaire. Co-authored by Charles Hoskinson, it is the first CIP he has gotten directly involved with. It’s clear a lot of thought went into it, and it’s intentionally written as a transitional, living document.

When Cardano was formed, there was a tripartite structure with Emurgo, the Cardano Foundation (CF), and IOG with remits for ecosystem growth, governance, and engineering, respectively. The intention was always to move to a members-based organization (MBO) that would manage the protocol governance. It was hoped originally that the Swiss-based CF would be this entity but due to limitations with the stiftung structure, it was not viable. 

CIP-1694 is the fruit of years of research. IOG has been working on a decentralized update system for some time. For example, they wrote a paper Updateable Blockchains with the European Union, with a Horizon 2020 grant, to explore ways to implement this vision. Like all CIPs, CIP-1694 is a living document which updates and evolves with feedback. While constitutions have been written before, we are entering uncharted waters as nothing on this scale has been attempted in the crypto space. Liquid democracy is not a new concept, but there are few examples of successful implementations. CIP-1694’s motivation is to bootstrap the Voltaire era, to integrate new and existing on-chain and off-chain components to self-govern the ecosystem. The ultimate goal is to have a governance layer on top of Cardano that is fully, end-to-end, on-chain. 

The CIP favors voting by stake over votes per person. One of the most important aspects of CIP 1694 is the notion of ‘one Lovelace, one vote’. Voting per person requires some notion of identity verification, so there is proof someone is who they claim to be. The CIP explains that a fully decentralized solution for this is currently not possible. With regulation varying by jurisdiction, it is prudent to steer clear of any mechanism that can be construed as ‘centralized’ by willfully ignorant parties. 

Early in 2022, IOG and the CF held workshops to hammer out a way forward for the Voltaire development phase. The first question was ‘What is good governance?’. Charles Hoskinson explained in his ScotFest keynote that the answer was based on three different categories:

The concept of representation involves consent regarding decision-making authority. There are two types: direct representation, where individuals vote personally, and delegated authority, where individuals hand their vote to someone else. In CIP-1694, this role is called a delegate representative (DRep). This concept was already introduced in a similar form in Project Catalyst. 


Governance requires a set of rules, often called a constitution, which serves as guardrails to provide stability. In a blockchain context, a constitution can be machine-readable. Formal specifications can act as blueprints for Cardano, enabling integration with an update system. Once a voting system is established, the constitution can be ratified, hashed, and embedded in a transaction. This allows users to sign a type of ‘end user agreement’ by signing the transaction.

Institutions are often seen as targets for decentralization. If the goal is to ‘kill the middleman’, why do institutions matter? At their best, institutions set standards and provide a review process conducted by domain experts. Institutions are essential for good governance as they are the custodians of knowledge and best practices. People can be biased, so objective, neutral bodies are sometimes necessary for guidance. After careful consideration, it was determined that the most important ‘anchor’ institution would be a members-based organization (MBO) which should operate similarly to other open-source initiatives like the Linux Foundation, or the Cloud Native Computing Foundation (CNCF).

IOG’s Chief Legal Officer Joel Telpner joined Charles Hoskinson for a fireside chat at ScotFest to discuss the challenges of drafting a new constitution. Telpner described what a constitution is:

I think you can actually simplify a constitution and say it's a set of rules, but it's a set of rules to do what? It does three things. It establishes how you legislate; it establishes how you administer and establishes how you adjudicate. It creates this framework for those three functions.


What is an MBO?

The MBO is a central hub that unites different groups, including thousands of stake pool operators, Cardano ambassadors, open-source projects running on Cardano, IOG, CF, Emurgo, and all ada holders. Members will own and run the MBO, staffing the steering committees. 


Figure 11.1. Governance concepts defined, based on the slide from ScotFest 2022

The MBO, later christened Intersect, is Voltaire's anchor institution, but it is not the only one. IOG has been steadily building out its presence in universities all over the globe, as well as opening the Hoskinson Center for Formal Mathematics, the Zero-Knowledge Lab not forgetting the Edinburgh Decentralization Index (EDI).  Other institutions and MBOs will follow with different focuses and priorities.  

‘Institutions… their only job is to take complexity and turn it into simplicity’ – Charles Hoskinson

CIP-1694 could fill a book on its own and, like all CIPs, is a living document that evolves with feedback. It aims to bootstrap the Voltaire development phase, integrating on-chain and off-chain components for ecosystem self-governance. The ultimate aim is a fully end-to-end, on-chain governance layer for Cardano.

Where we were – the five out of seven system

Before the Chang hard fork, governance transactions (eg, hard forks, parameter changes, etc) required a signature from at least five out of the seven Cardano governance (genesis) keys, held by the three founding entities. This process was always intended to be an ephemeral form of governance as we got through the earlier phases of the roadmap before Voltaire. There have traditionally been just two types of governance transactions:

Protocol parameter updates using transaction field nº6 of the transaction body
Movements of the treasury and the reserves using Move Instantaneous Rewards (MIR) certificates.
Where we are going

The current proposal encompasses two new ledger eras. The first era is called Conway, after the celebrated English mathematician John Horton Conway. The current plan for the Conway ledger era is to:

introduce SPO voting for hard forks 
provide an on-chain mechanism for rotating the governance keys
rewire the ledger rules involving governance as outlined in CIP-1694.

For CIP-1694 to succeed, it is essential to realize the vision presented in the Road to a Polyglot Ecosystem for Cardano whiteboard video. The new governance mechanisms will enable the development of multiple clients, enabling different development teams to employ different approaches, programming languages, and commercial unique selling propositions (USPs). 

Charles Hoskinson’s keynote at ScotFest 2022:

‘So that's Voltaire …it’s deeply philosophical, it's the hardest thing I've ever done in my life, it's the hardest thing you're ever going to do in your life, and we're going to get it done, because it needs to get done and I'm damn tired of our industry failing, and it's about time we can point to something and say ‘you know what, we did it the right way’. We have to tend to our own gardens first. That was a lesson of Candide. So we have to fix Cardano's governance before we have the right to complain about any other person's governance.’ 

2023 was all about debating how to implement CIP-1694. The CIP was written in a deliberately high-level, approachable format to stimulate discussion and feedback. The community did not disappoint with 50 workshops, 30 in-person and 20 online, with over 1,000 participants from 20+ countries. 

In addition to community-led workshops, IOG, EMURGO, and the Cardano Foundation co-hosted three governance workshops. The CF workshop took place in Zug, Switzerland, in June, followed by EMURGO’s workshop in Tokyo, Japan. The final workshop, hosted by IOG in Edinburgh in July 2023, marked the conclusion of the CIP-1694 design feedback loop.

Dozens of blogs have been written, and contentious issues have been argued over Reddit, X (Twitter), and Telegram. It is impossible to acknowledge every voice here, but you can dig into the finer detail by following Nicolas Cerny’s diary of events on the Cardano Forum. 

Governance on Cardano hit a milestone on Friday, June 30, 2023, when the CIP-1694 pull request was merged into the main branch of the Cardano Foundation CIP repository. The proposal’s status advanced to the ‘Proposed’ stage.

As almost everything in Cardano takes the form of a transaction, getting the metadata standard correct is critical. Metadata allows developers to embed information specific to the context of the transaction. For example, the NFT standard (see CIP-25, CIP-68, CIP-60) on Cardano has evolved with new capabilities, unlocking with each roadmap release. Pi Lanningham authored CIP-0100 to clear up what metadata standards need to be introduced to enable the on-chain governance mechanisms proposed in CIP-1694. Building on top of CIP-0100, subsequent governance metadata CIPs have been drafted for Governance Actions (CIP-0108), DReps (CIP-0119), and the CC (CIP-0136).  

CIP-95 is a crucial CIP, which extends CIP-30 and describes the interface between webpage/web-based stacks and Cardano wallets. More specifically, it is a specification that defines the API of the JavaScript object that is injected into web applications. The CIP enables voting capabilities for governance tools. At the Edinburgh hackathon, decisions were made around open questions, and the base design was approved. 

As governance can be subjective, it's best you read CIP-1694 yourself, especially the Rationale and Changelog sections, which add context. If 2023 was the year we discussed governance, 2024 was all about implementation with Intersect as the main driving force. 
Intersect
Intersect is a members-based organization for the Cardano ecosystem, founded in 2023. It serves as an aggregation point for the entire Cardano community, placing the community at the heart of Cardano’s future development and harnessing the untapped potential of collective wisdom and economic energy. Intersect brings together companies, developers, individuals, institutions, and other ecosystem participants to shape and drive the future development of Cardano. It acts as a steward of the underlying blueprints and technology for the community, beginning with the Cardano node, core technology libraries, and components required to operate the protocol, along with all of its accompanying documentation, knowledge, and contributors.

This governance structure is designed to enhance decentralized growth within the Cardano ecosystem. It enables community-driven decision-making through democratic voting, defines clear roles and responsibilities, and ensures accountability. The MBO manages funds for ecosystem projects, aligns efforts with long-term strategic goals, and fosters inclusive community participation. It also improves coordination, increases accountability, and supports sustainable growth by providing a structured yet decentralized framework. Implementation involves community consensus, framework development, regulatory compliance, securing funding, and ongoing management. This model empowers the Cardano community and aligns with its vision of decentralization and transparency.

Intersect empowers a distributed network of builders and contributors who believe that every voice holds value and that collaboration leads to stronger outcomes. Members forge a secure, collaborative ecosystem to ensure Cardano's sustained growth and evolution in a safe space.

How Intersect operates
Intersect aims to administer the governing processes for Cardano’s continued roadmap and development of the Cardano protocol. Intersect is currently facilitating the rollout of Cardano’s governance features. Visit the Intersect latest news page to keep up to speed with the latest developments. 

All Cardano ecosystem participants are welcome to become Intersect members. Made up of a distributed group of participants, including the foremost experts on Cardano and current ecosystem contributors, Intersect aims to facilitate healthy discussions and sound decision-making amongst its members and the community to uncover pain points and champion successes.
The five pillars of Intersect
Community support for hosting events, hackathons, and conferences targeting developer adoption
Governance: championing and overseeing Cardano's community-driven governance system, implemented through CIP-1694
Technical roadmap: orchestrate the delivery of the Cardano technical roadmap with community approval.
Continuity by ensuring system stability, Intersect facilitates Cardano's ongoing continuity
Open-source development by coordinating the open-source development of Cardano's core technologies.
Intersect has a central governing board, similar to a city council, chosen and managed by its members. This board is supported by various committees and working groups, each focusing on specific areas or interests within the Cardano ecosystem. With its diverse global membership, this structure allows Intersect to effectively identify key goals for Cardano's development.

Intersect's governing board starts with five seats. Three are filled by founding members (Gerard Moroney from Input Output, and Nikhil Joshi of EMURGO), with the Intersect chief operating officer (COO) holding a temporary seat. Another seat is offered to the University of Wyoming's Blockchain Center for a one-year term, held by Steve Lupien. The remaining two permanent seats were filled later in 2024 by Intersect members, Adam Rusch and Kavinda Kariyapperuma, through an election process.

A new advisory board will be created with member input to find the best people for the remaining board seats. This group will also explore how to hold elections for future committees. The board meets monthly and publishes agendas and minutes for transparency, and can be contacted at board@intersectmbo.org.

A community working group was formed in January 2024 to support transparency. This group observes board meetings and gathers community feedback to ensure Intersect meets members' needs. 

Intersect's funding

Intersect uses funding to promote open and accessible systems through technology and education and to shape Cardano's development. This includes running Intersect itself and supporting the open-source development of Cardano's technology.

Input Output Global and EMURGO initially funded Intersect to get things running. For future funding, the community will be asked to vote on using funds from the Cardano treasury or explore other options.

Maintaining and improving Cardano requires ongoing costs. For 2024, Input Output Global and EMURGO have provided funding to cover these operational costs. This allows a group of members to continue providing essential technical services. Intersect created the Cardano development trust (DevTrust) to manage these initial funds. This trust can only use funds to benefit Cardano, such as funding ongoing development and honoring existing agreements. Intersect manages the DevTrust to ensure these funds are used appropriately and to generate income to support its operations.

Becoming a founding member comes with the following benefits:

Participate in steering groups, committees, and advisory boards, with the potential to establish new committees that will define Cardano's future governance
Access grants and contribute to developing Cardano's codebase while guiding a grant program to strengthen the Cardano protocol and ecosystem
Collaborate with other Cardano enthusiasts to build new partnerships and connections
Showcase contributions through member events, conferences, marketing materials, and member spotlights
Attend monthly meetings for updates on progress, committees, events, and funding opportunities 
Participate in the annual meeting (in-person or virtually), focusing on Intersect activities, including voting on proposals. There are many Community Hubs, located worldwide, hosting events.
Amending Intersect membership governance
Proposals to change Intersect's membership governance must be clearly documented. The board can approve amendments by a simple majority vote. There are various streams regarding the ongoing work that maintains and improves Cardano.

Think of ‘continuity’ as the essential technical services needed to keep Cardano running smoothly. This includes bug fixes, upgrades, and new developments like CIP-1694. In the first quarter of 2024, Intersect signed several contracts to deliver features and functionalities through continuity efforts. It's important to note that continuity focuses on the core infrastructure and many other exciting community projects and applications are being built on top.

Cardano's vision and backlog refer to Cardano's future development, including new features and functionalities. These features may still be in the research phase or identified by the community for further exploration.
Open-source development
Cardano is an open-source project, with over 40 code repositories maintained by Intersect and its members. You can find more information by exploring Intersect’s GitHub repositories.

True open source means having the flexibility to choose different options. The Cardano Foundation also follows an open-source strategy. Ledger Sync, Identity Wallet, Aiken, Kupo, and Ogmios all follow open-source principles and make life easier for developers on Cardano. 

Acknowledging that Java is still the preferred language for many enterprise developers, the CF created Ledger Sync and the Identity Wallet in Java as open-source tools with this audience in mind. Ledger Sync puts sequential blockchain data in a new, more accessible database structure, while the Identity Wallet is a W3C-compatible mobile wallet for managing self-sovereign identities across Cardano and other blockchains. The wallet supports multiple standards, integrating key event receipt infrastructure (KERI) for interoperability to fit a broad range of use cases and enterprise adoption.

In addition, The Cardano Ballot project, a Merkle Tree in Java/Aiken, the Cardano conversions library, and state channels layer 2 (hydra-java Client) were all made open source. The CF also made the rewards calculation open source to enable anyone to perform and validate the rewards calculation independently of a single implementation. 
Open source office (OSO)
The OSO manages Cardano's open-source program and community. They ensure open and effective communication with the wider open-source community. Intersect manages contracts with companies working on Cardano's development, acting on behalf of DevTrust.

Intersect handles all aspects of supplier contracts for DevTrust. This includes negotiating terms, managing the agreements, and overseeing the work. Intersect ensures the contracts align with DevTrust's goals and that companies meet their obligations. They also monitor progress and take steps to optimize efficiency and keep the community informed.

Delivery assurance

Delivery assurance ensures that projects are completed on time and according to specifications. This involves managing risks, tracking progress, and taking action to ensure successful completion. The approach varies based on the project's size, complexity, and potential risks.

Led by the technical steering committee (TSC), Intersect's delivery assurance team plays a vital role. This team works on behalf of the Cardano community to guarantee that Cardano's development plan stays on track.

Intersect's role in development
Intersect awarded contracts to seven of its members. These contracts focus on continued development efforts, ensuring Cardano can deliver the exciting new features the community awaits. Here's a breakdown of just some of the work ongoing:
Input Output Global’s (IOG) infrastructure team continues to develop and test the Cardano node
Galois works on zero-knowledge proofs (ZKPs) to enable interoperability between Cardano and other chains.
Welltyped is developing Log Structured Merge Tree implementations, which will store the ledger's UTXO set on disk rather than in memory. There are many benefits as a result: an increased number of UTXOs will improve bandwidth, facilitating more users. Nodes will be able to run on cheaper, lower-spec machines.
Tweag’s focus is on the Ouroboros Genesis mechanism, enabling new nodes to seamlessly (re)join the network securely.
Vacuum Labs ensures the continued smooth operation and functionality of Ledger and Trezor hardware wallets for the Cardano community, with enhancements planned for the Conway era.
Byron leads the launch and beta testing phase of the GovTool web application. This involves identifying and fixing bugs while gathering valuable user feedback.
DQuadrant is developing a suite of web application tools to support Cardano's evolving governance system. 
EMURGO creates educational resources to explain the core concepts of CIP-1694.

As grants are continuously offered over different cohorts, it’s best to check for the latest on the Intersect website. 
Committees & working groups
Intersect operates on the principle of community leadership for Cardano's development. This is achieved through standing committees formed by and led by its members.

Standing committees are permanent committees covering various functions critical to guiding Cardano's ‘continuity’ (ongoing maintenance and development), shaping Cardano's constitution, and supporting internal membership needs. While changes can be made as the committees and their goals evolve, they are intended to be long-lasting. The governing board will provide support and review any proposed adjustments.
Intersect steering committee
The Intersect Steering Committee is like an umbrella committee, bringing together the chairs of the other Committees with the Functional Administration Leads of Intersect to enable collective decision-making and thinking. 
The civics committee

The civics committee acts as a guide and supervisor, providing oversight for the Cardano community on governance issues: 

Facilitate the timeline for the ratification of the constitution 
Manage and administer the archive of off-chain talks about proposals
Act as a watchdog for governance tools, ensuring they’re working and maintained properly
Create documentation and standards for on-chain voting
They collaborate with subject matter experts from the community and offer non-binding recommendations to improve governance as appropriate 
They assist the Cardano constitutional committee as requested.

This committee is crucial for ensuring Cardano's governance system is:
Accessible: easy for everyone to understand and participate in
Fair: upholding equal rights and opportunities for all community members
Transparent: open and clear communication about all governance processes.

Membership and community committee (MCC) 
The MCC helps build a strong Cardano community within Intersect. They achieve this by:

Attracting new members through effective sales and account management
Supporting existing members through helpful resources and events
Offering grants for creating useful community tools
Providing education and hosting engaging events.

This committee creates a space for Cardano enthusiasts to connect, share knowledge, and collaborate on projects. For example, a grant was awarded to Ryan Wiley for his ‘Cardano Governance Minimum Attack Vector (MAV) Dashboard’. This tool displays real-time governance action data through donut charts, breaking down participation in governance actions by DReps, SPOs, the CC, and an aggregated total of all groups. This highlights which entities sway over each proposal type based on stake-weighted delegation and voting thresholds. Anyone in the Cardano ecosystem can flag specific centralization concerns with this user-friendly dashboard.

The MCC manages Intersect memberships, ensuring everyone gets the most out of the program and can contribute to Cardano's development. They also review proposals for community working groups.

Want to learn more or join the MCC? Email them at membership-and-community-committee@intersectmbo.org. They hold public meetings every four weeks, and their minutes are public. Check out the MCC terms of reference (ToR) for a deeper dive.

The technical steering committee (TSC)

The TSC oversees Cardano's technical health, ensuring that decisions are based on solid technical knowledge and best practices.

This committee brings together key players to ensure Cardano's development runs smoothly. They handle contracts with developers, create technical proposals, and review ideas from the Cardano community, like updates or major changes to the network.

The TSC leads in guiding the development of Cardano's ongoing technical foundation. They provide in-depth technical analysis and advice for everything from development projects to network settings. Think of them as the guardians of Cardano's technical well-being. The minutes from their meetings are public. Check out the Intersect GitBook for further details on the TSC and its working groups.

The parameter committee (PC)
The PC is a subteam of the TSC that focuses on optimizing Cardano's settings. They ensure these parameters are set based on the best technical knowledge available.

This committee plays a crucial role in maintaining Cardano's long-term health. They consider factors like economics, security, and network performance when recommending updates to Cardano's core settings.

The PC delves into Cardano's parameters, including technical settings, network behavior, and economic factors. They meet regularly to discuss updates and consider proposals from the community to adjust these parameters.

Membership in this technical group is by invitation only. However, anyone can submit suggestions for parameter changes on the Cardano Forum. The PC also participates in monthly calls with Cardano's stake pool operators to share updates and answer questions. 

Matthew Capps’ X thread, Protocol Change Proposal-001: Chronology of Documented Events, provides insight into the careful consideration and deliberation involved in a parameter change.

To learn more, check out the meeting notes and learn how to submit parameter change proposals on the Cardano Forum.

The open source committee (OSC)

The OSC owns the roadmap (strategy) for Cardano's open-source projects, advising others on open-source best practices, and acts as a central point for anyone building within Cardano's open-source environment.

This committee helps developers navigate the world of open-source development on Cardano.

The OSC tackles several key areas:

Defining what ‘open source’ means for Cardano projects
Developing and maintaining Cardano's open-source strategy
Overseeing pilot projects for open source on Cardano
Establishing best practices for open-source development within Cardano
Creating a model for future open-source projects within Intersect.

The OSC was the first Intersect committee and is currently chaired by Tweag. Anyone can join the OSC's weekly public call on Fridays (8-9 AM PST) to learn more and ask questions. They also have a Discord channel (#osc-feedback) for ongoing discussions.

Check out the latest meeting notes, their governance policy, and a community-drafted voting procedure proposal.

Cardano budget committee  

The Cardano Constitution necessitates an annual budget process. A budget committee manages Cardano's operational costs and shoulders arguably the most important, and controversial, task of drafting a yearly budget for community review, approval and ultimately on-chain ratification. The committee strives to provide clear information on Cardano's core expenses, ensuring transparency for the community.

How it will work:

The committee will manage the annual budget process which involves managing working groups, allocating buckets, liaising with DReps, audit and oversight, managing the treasury  
Communicate back to the community updates on the above. 

Figure 11.2: Provisional Budget process timeline


Product committee  
The product committee manages and tracks the roadmap for development items. This encompasses:

Continuity, in other words, maintenance, upgrades, and core development, feature requests
Research. 
Marketing, promotion, or other non-technical categories.

People were encouraged to submit projects for consideration for the 2025 roadmap, with an explainer to guide them through the process.


Working groups
Working groups are temporary and typically support a standing committee's broader objectives. They may also be formed to tap into expertise outside of Intersect's membership. Flexible and less formal than committees, working groups can address diverse topics relevant to Cardano's development.

There are too many to cover, but there is something for everyone with various Technical Working Groups and Special Interest Groups. For example, the marketing working group was formed by creatives and marketers who felt it was an area Cardano could improve upon. The group meets weekly and is active on Discord.

To learn more, head over to the Intersect working groups space for a complete list and further details. 

The first of six Annual Members Meeting was held in Tokyo in October 2024. The Japan Intersect Hub, led by Yuta and Yuri, sixty-nine members attended and celebrated the successes this year, with a look ahead to 2025 and areas we can improve on.

Towards the end of 2024, Intersect held elections for open positions for the various committees and boards we just went through. The successful candidates were:

Intersect board -  Kavinda Kariyapperuma, Adam Rusch
Intersect steering committee - Yuki Oishi, Kevin Hammond
Budget committee - Mercy Fordwoo, Jose Velazquez, Kristijan Kowalsky, Pepe Otegui
Cardano civics committee - Reshan Fernando, Taichi Yokoyama, Eystein Magnus Hansen, Daniela Alves
Membership and community committee - Sanjaya Wanigasekera, Matthew Capps, Ha Nguyen, Akheel Fouze, Darlington Wleh
Open source committee - Adam Dean, Johnny Kelly, Sebastian Pabon, Pedro Lucas
Product committee - Naushad Fouze, Samuel Leathers, Juan Sierra, Kyle Solomon
Technical steering committee - Adam Dean, Kevin Hammond, Markus Gufler, Ben Hart, Johnny Kelly 


Governance entities and roles
Cardano's future governance leans on three key pillars:
On-chain decisions: this system (detailed in CIP-1694) allows ada holders to directly influence Cardano's development through proposed governance actions voted on-chain
Cardano constitution: this evolving document outlines core rules to guide Cardano's growth during its transitional governance phase. A fully-fledged constitution was drafted with community input throughout 2024, culminating in a final version ratified by delegates at the Convention in December. Finally, it must be ratified by ada holders in an on-chain vote after the Plomin hard fork.  CIP-0120 (constitution specification) proposes a standardized technical format to make the document accessible for tools to read, render, and write. 
Institutions: these provide spaces for discussion, collaboration, and recommendations that ultimately feed into on-chain decision-making.
These three elements work together to create a robust governance system that can adapt and improve over time, driven by the Cardano community. We are now over two years into the age of Voltaire, and four key roles continue to be pivotal as CIP-1694 becomes a reality.
Ada holders
Ada holders play a crucial role in Cardano's governance. They can:

Delegate their vote: choose representatives (DReps) to cast votes on their behalf
Become a DRep: represent themselves or others in on-chain voting
Shape Cardano's future: propose changes to the network by submitting on-chain governance actions
Stay informed: review submitted governance actions and cast their vote on them.

By actively participating, ada holders collectively drive Cardano's development.
DReps
The age of Voltaire introduced delegate representatives (DReps). This new concept, central to Cardano’s governance, is defined in CIP-1694. DReps,  alongside stake pool operators and the constitutional committee, vote on proposals that shape Cardano's future.

Any ada holder can become a DRep. This means ada holders can choose to directly participate in voting or delegate their voting power to DReps they trust. There are two predefined DReps: the abstain and the no confidence DReps. These options allow ada holders to either not participate in governance or automatically express a yes vote on any no confidence action, providing a directly auditable measure of confidence in the constitutional committee.

DRep delegation piggybacks on the existing stake delegation and registration mechanisms. Just like when the ada delegated to a pool is not moved anywhere, ada delegated to a DRep is not transferred anywhere either. Also like delegated ada, you can choose to re-delegate from DRep to DRep at any time.

Ouroboros has been a huge success story, with a large majority of ada staked making Cardano one of the most decentralized networks. By leveraging the SPO network, the process gains a passionate Cardano user group who are educated and qualified to vote on crucial decisions. Registered DReps are expected to vote on governance actions regularly to still be considered active. It will be measured using a new parameter called ‘drepActivity’. Inactive DReps won’t count towards the active voting stake, but can become active again by resuming voting.
Why delegate? 
Delegation allows ada holders to empower representatives who are potentially better equipped to make informed decisions on their behalf. This fosters a more democratic system where everyone has a say, even if they don't have the time or expertise to delve into every proposal.
Throughout 2024, Intersect collaborated with the IOG education team on the DRep Pioneer program, an online interactive training course for nominated DReps involved in Cardano’s proposed governance structure. These pioneering DReps played an important role in educating the community. 

Intersect was inundated with applications from candidates. After a meticulous selection process, the initial cohort was announced. Pedro Lucas, Martin Musagara, Ha Nguyen, Cameron Smith, Joao Bosco Ribeiro, Reshma Mohan, Daniela Alvez, Phil Lewis, Eystein Magnus Hansen, Ubio Obu, Jaromir Tesar, Adam Rusch, Jenny Brito, Hosky and Wada Global Ltd represent the diversity of the global Cardano ecosystem.


The first community DRep workshop took place on January 20, 2024, in Oslo. This initiative was funded by a Catalyst Fund10 proposal from Eystein Hansen, Adam Rusch, Ekow Harding, Jose De Gamboa, Thomas Lindseth, and Yuki Oishi. Many more workshops followed. Intersect member LIDO Nation created the DRep Campaign Platform which enables DReps to create off-chain profiles linked to their on-chain actions to campaign for delegation from Ada Holders. 


Stake pool operators (SPOs)


Think of SPOs as the caretakers of Cardano's network. They run stake pools, which are essentially servers that keep the blockchain running smoothly. These operators typically:

Own or rent servers running the Cardano node (both block-producing and relay nodes) 
Hold the pool's key
Maintain and monitor the network nodes.

SPOs play a vital part in Cardano's on-chain voting governance by:

Proposing changes: they can submit governance actions to improve the network
Shaping the future: they can review and vote on proposed governance actions.

The constitutional committee (CC)
Unlike other Cardano governance bodies, the CC operates independently and entirely outside of Intersect. It is one of three key groups (alongside SPOs and DReps) that vote on proposals to change Cardano's core systems through governance actions. The CC's primary function is to review proposed changes with a limited focus: ensuring that they align with the principles outlined in Cardano's constitution.
Governance flow
CIP-1694 outlines Cardano's on-chain governance process, but it's also important to consider the supporting off-chain activities. 
Off-chain proposal discussions

Before proposals are submitted to the blockchain for official votes, there is a crucial off-chain stage for discussion and refinement. Off-chain debate allows for clearer proposals, community input and informed voters. It reduces on chain bloat by filtering and refining proposals off-chain lowering the number of votes submitted on-chain. 

Without a strong off-chain process, governance could falter, as ideas may not undergo thorough discussion or refinement. On-chain proposals might lack the necessary context, making informed voting difficult.

Intersect recognizes the importance of off-chain discussions and has issued a grant to establish a dedicated proposal discussion forum. More information about the grant can be found in Intersect's GitBook.

Submitting on-chain governance actions
Once a proposal has been thoroughly discussed and refined off-chain, it is ready for the official vote on the blockchain. This is known as on-chain governance action submission. Proposals can be submitted on-chain through the Cardano command-line interface (CLI) or via GovTool’s user-friendly interface. The specific content required for an on-chain proposal depends on the type of governance action being submitted. Proposers can optionally add metadata to provide additional context and information alongside the proposal. 
Register as a DRep
DRep registration occurs on the blockchain and can be done through the Cardano CLI or GovTool. During registration, DReps can optionally add details about themselves (metadata) to help ada holders decide who to delegate their votes to.

Intersect recognizes the importance of a strong DRep system and has issued a grant to establish a DRep campaign platform. 

On-chain DRep delegation

On-chain delegation allows ada holders to give their voting power to a DRep of their choice. These DReps then cast votes on their behalf regarding active governance actions.

To make an informed decision, individuals should review the metadata submitted by DReps during registration. This metadata might include details like their expertise, areas of interest, and even past voting history.

The delegation process happens on the blockchain and can be done through the Cardano CLI or GovTool.

On-chain voting process

On-chain voting is where the three voting groups (DReps, SPOs, and the CC) cast their votes on active governance actions.

For a proposed governance action to be approved and implemented, it needs to meet specific voting thresholds set by Cardano. These thresholds may vary depending on the type of governance action being voted on. In simpler terms, some proposals might require approval from all three voting groups, while others might only need a certain percentage from a specific group.



Figure 11.3: Voting on governance actions (table from Intersect’s documentation)
Following the on-chain voting process, a governance action is considered approved (or ratified) if it meets the specific voting thresholds set for its type. These thresholds determine the level of consensus needed from the different voting bodies.

Once ratified, a governance action is then enacted on-chain, meaning it's implemented and becomes part of the Cardano protocol according to a well-defined set of rules.

Proposals categorized as Info actions are a special case. Since their purpose is solely to provide information, they don't require enactment and have no impact on the protocol itself. Their ratification simply acknowledges their informational value.

Cardano's governance process emphasizes open communication. This includes not just discussing proposed governance actions beforehand, but also sharing their outcomes after the on-chain voting is complete.

A complete governance cycle starts with off-chain discussions and should end with the community being informed of the outcome. Sharing results, especially for ratified (approved) proposals that will be implemented, helps close the loop and keeps everyone informed.

Ideally, the outcome should be communicated through the same off-chain channels where the original proposal was discussed. This fosters transparency and a sense of connection throughout the entire governance process.

SanchoNet
SanchoNet was named after the character Sancho Panza, Don Quixote’s companion in Miguel de Cervantes’ literary classic. SanchoNet is ultimately about transforming an aspirational digital Barataria into an on-chain governance reality on Cardano mainnet. Note that SanchoNet is not another incentivized testnet (ITN), but a testnet where test ada is used to stress test experimental features. SanchoNet was rolled out in six phases, with each Cardano node (cardano-cli) release enabling new governance capabilities. 

Figure 11.4: SanchoNet roadmap
SanchoNet goes beyond simple testing. It also serves as a platform for informing the community, engaging stakeholders and building a collaborative future. 
SanchoNet’s capabilities have been continually enhanced. For example, support for governance metadata standards CIP-100 and CIP-108. SundaeLabs developed CIP-100 to settle on a standard for all CIP-1694-related off-chain metadata. 


SanchoNet has proven itself robust to adversarial behavior. Mike Hornan of Able Pool SPO orchestrated a sustained community-driven stress test on SanchoNet, ensuring the network has the required resilience to handle thousands of governance actions concurrently.

SanchoNet has allowed users to experiment with upcoming features. For example, SanchoNet users were the first to test PlutusV3 in Conway-era transactions. PlutusV3 opened up a world of possibilities with a new voting script purpose for writing voting scripts, access to governance actions in the ScriptContext, and new cryptographic Plutus primitives.

Governance tools
For Cardano's vision as a truly decentralized blockchain to become a reality, it requires more than just principles and processes. It needs the right tools to empower the community and enable consensus across the Cardano ecosystem. The development of Cardano's on-chain governance prioritizes building these tools. This will create a smoother experience and open new avenues for community involvement in shaping Cardano's future.

These governance tools will be open source and owned by the community. Through its committees and working groups, Intersect will play a role in hosting and maintaining them with community approval. The goal is to build this foundation with various Cardano ecosystem developers.

Once the core set of tools is established, the community can further contribute by:

Maintaining and improving existing features
Creating entirely new functionalities or tools
Working independently or collaborating with Intersect's grant and award programs.

These tools will equip the Cardano community to actively participate in on-chain governance actions. Intersect has already issued grants to develop key components of this toolset.  The governance tools working group has begun decentralizing ownership and maintaining the GovTool and constitutional committee portal.

GovTool
The GovTool is a central hub for interacting with Cardano's on-chain governance system, and testing upcoming features. It enables users to connect their wallets to mainnet to participate in governance. They can also connect to SanchoNet, the testnet environment where CIP-1694's ideas are tested.

The GovTool empowers the Cardano community to:

Register as a DRep, delegate voting power to a DRep, vote, and much more. There are extensive guides available.
Shape the future by providing feedback on their experiences, enabling the community to help refine Cardano’s governance framework for future implementation.

GovTool is not the only governance tool. Cardano ballot is another innovative voting system designed for Cardano's governance process. It combines the strengths of both on-chain and off-chain mechanisms, developed by the Cardano Foundation and IOG. It is open source, and contributions are welcome on GitHub.

Governance actions
Governance actions is the term used for proposals submitted for on-chain voting. These proposals trigger events on the blockchain through transactions and have a set timeframe for voting before they expire and can't be enacted. Any ada holder can submit a governance action for on-chain voting. Once a proposal is submitted and recorded on the ledger, voters can vote through separate voting transactions.

CIP-1694 defines seven categories of governance actions:
Motion of no-confidence: creates a state of no-confidence in the current constitutional committee
New constitutional committee or quorum size: proposes a change to the members of the constitutional committee and/or to its signature threshold and/or terms
Updates to the constitution: proposes a change to the off-chain constitution, recorded as an on-chain hash of the text document
Hard fork initiation: triggers a non-backward compatible upgrade of the network
Protocol parameter changes: proposes a change to one or more updatable protocol parameters
Treasury withdrawals: proposals for how to spend funds from the Cardano treasury
Info: simply provide information and don't require enactment.


The Chang hard fork
The September 1st 2024 upgrade was named after Phillip Chang, who passed away in 2022, in honor of his contribution to the early design and concepts described in CIP-1694. The Chang upgrade marked a significant moment for Cardano, representing the culmination of years of dedicated development and community involvement. Extensive testing on SanchoNet and valuable feedback from community workshops have paved the way for this critical step.

From Basho to Voltaire: a self-sustaining future

With this milestone, Cardano transitioned from the Basho development phase to Voltaire. This upgrade series unlocked minimum viable on-chain governance as outlined in CIP-1694, empowering the community through a self-sustaining blockchain model that sets a new standard for the industry.
The Plomin hard fork
Initially named Chang upgrade #2, it was subsequently renamed to honour Matthew Plomin, the founder and visionary behind Moneta and USDM stablecoin, who passed away suddenly in November 2024. The Change hard fork was the initial upgrade that introduced core governance functionalities, initiating the technical bootstrapping phase as defined in CIP-1694. This took Cardano into the Conway ledger era and officially heralded the start of Voltaire. The Plomin hard fork unlocked the full potential of on-chain governance, enabling DRep participation and treasury withdrawal capabilities. This marked the completion of the technical bootstrapping phase.

Cardano's on-chain governance relies on a core document: the ratified constitution. This document, approved through the new governance features, establishes the fundamental rules and principles that guide Cardano's operation.

Technical guardrails for stability

The Intersect governance parameters working group shared their report and recommendations on the initial settings to be included in the technical guardrails as Cardano passed through these hard forks. To ensure adherence to the constitution, a smart contract acts as the technical guardrail. This contract translates key constitutional provisions into code, wherever possible. For example, it might define acceptable ranges for parameters or treasury withdrawals so the blockchain will automatically reject any governance actions that violate these guardrails, preventing actions deemed unconstitutional. You can review the Aiken version on GitHub under acceptance tests. This adds an extra layer of security and stability to Cardano's governance process.

Intersect convenes and organizes the hard fork working group’s meetings. Over 60 people from 10 organizations participated, ensuring that the views and perspectives of many backgrounds are considered. The Plomin upgrade followed Cardano’s usual deployment strategy with the final decision to initiate the upgrade based on three key factors:

Technical stability: no critical issues were identified within core components (ie, ledger, node, consensus, and CLI) 
Performance optimization: benchmarking and analysis ensured acceptable performance and cost implications
Community readiness: sufficient communication and preparation time was provided to SPOs, DApp developers, and the broader Cardano community.

This measured approach, explained in more detail in the documentation, ensures a smooth transition for all stakeholders. There were additional actions required this time, however. The Plomin hard fork was the first in the age of community-led governance, also the first one not initiated by the genesis entities. Instead, it was submitted as a Hard Fork Initiation Governance Action. For it to pass, it needed two approvals:

Required two-thirds approval from the Interim Constitutional Committee (ICC) who assessed its constitutionality.
A 51% approval from SPOs, measured by total active voting stake delegated to stake pools.

Stake Pool Operators (SPOs) were encouraged to also consider the ecosystem readiness when voting on the Hard Fork Governance Action (GA). The Plomin Upgrade Readiness page was keenly followed by those tracking hard fork readiness.

Path to Ratification 
The interim Constitution was drafted early in 2024, and along with the technical guardrails, was made available for the community to read on the Constitution Committee Portal. The first interim Constitutional Committee (ICC), the body that upholds the interim Constitution and votes on the first on-chain governance actions, was formed. The community voted for three representatives to sit alongside pioneer entities IOG, EMURGO, and the Cardano Foundation, and Intersect. The Cardano Atlantic Council, Cardano Japan, and Eastern Cardano Council were duly elected to this responsible position. 

The constitution can only claim legitimacy with feedback from the community, and so the first of 64 workshops covering 51 countries in six of the seven continents was hosted by Nicolas Cerny, Governance Lead for the Cardano Foundation, in Berlin in July 2024. The Cardano Foundation submitted their amended constitution proposal, and explained in detail their suggested amendments and reasoning. The overarching purpose for the changes was to improve the accessibility and clarity, particularly for a less technical audience.

The feedback was collated and 128 delegates (64 voting, 64 traveling alternates) were chosen to attend the constitutional convention in Buenos Aires, Argentina and Nairobi, Kenya, in early December 2024. After two days of debate and speeches, the constitution was approved by 95% of delegates. 

This milestone was met with much celebration and tears of joy, however, it is only the first of two votes. The real ‘moment of truth’ looms on the horizon when all ada holders will participate in an on-chain constitution vote when a governance action is submitted after the Plomin hard fork. This is provisionally earmarked for early 2025.

The 2025 Cardano budget will be defined through a community-driven process. With on-chain approval from the community, funding will come from the Cardano treasury. Intersect will continue to manage and oversee the technical delivery of such continuity services. Additionally, they are developing a backlog and budget proposal, which will form the foundation for Cardano's first official budget.
Pragma
From the outset of the Voltaire development phase, it was always expected, and some feel necessary, to have multiple MBOs. PRAGMA was announced on the eve of the inaugural BuidlFest meetup in Toulouse, France. PRAGMA is a member-based, not-for-profit, open-source association for blockchain software projects. Initially, it will be made up of familiar faces from the Cardano developer ecosystem: Blink Labs, Cardano Foundation, dcSpark, SundaeLabs, and TxPipe, but will expand to incorporate more projects and members in 2025. 


PRAGMA will not compete with Intersect, but run as a complementary effort. While the mission of Intersect is broader, PRAGMA is focused solely on open-source software development with two key projects for now: Aiken, the popular programming language for on-chain smart contracts on Cardano, and Amaru, a Rust node client for Cardano. You may get the impression there is only one budget from Intersect, but anyone can submit a budget proposal. For example, Amaru have a draft budget proposal outlining their vision for 2025. 


For Cardano to thrive, PRAGMA and Intersect need to work together to deliver what is best for the ecosystem.




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
