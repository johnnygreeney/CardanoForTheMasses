# Chapter 10: Catalyst for change


‘No problem can withstand the assault of sustained thinking.’ 
                                                                                     
							    - Voltaire

### to do: add markdown format

Money is social  
With a few noteworthy exceptions most blockchains have made no provision for future upgrades. The capacity to effectively drive a soft or hard fork is critical to a cryptocurrency’s long-term viability. As a result, investors are unlikely to spend millions of dollars on protocols whose roadmap and participants are fleeting, petty, or extremist. There must be an efficient procedure for forming agreement on a vision for the underlying protocol’s evolution. Fragmentation might split the group apart if this process is difficult.

Cryptocurrencies are an excellent illustration of money’s social component. When comparing Bitcoin, Litecoin and Dogecoin merely on the basis of technology, there is little difference between the three. Despite this, both Litecoin and Dogecoin have relatively large market capitalizations, active communities, and their own social agendas.

It might be claimed that a significant portion of a cryptocurrency’s worth is generated from its community, how they use their funds, and how involved they are in the currency’s progress. Adding to the idea, other currencies, such as Dash,Tezos and Polkdot have built methods directly into the protocol to allow its users to vote on what should be prioritized for development and funding.

The huge variety of cryptocurrencies also demonstrates their social aspects. Fragmentation and forks result from disagreements over philosophy, monetary policy, or even petty squabbling amongst the core developers. CH at ScotFest 2022:

People fall out over values, not facts

Unlike their digital cousins, fiat currencies tend to weather political upheavals and local disputes without a currency crisis. It seems that certain aspects of legacy systems are absent from the crypto sector. Cardano’s stance is that protocol users need incentives to understand the social contract that underpins their system and the opportunity to suggest modifications in a constructive manner. This independence applies to every facet of a value exchange system, from market regulation to project funding. However, it cannot be mediated by central actors, nor does it need any credential that may be co-opted by a privileged few.

Funding invariably dries up, regardless of the success of a crowdsale to bootstrap development. As a result, Cardano contains a treasury that reduces inflation and transaction fees over time. Through a ballot mechanism, any user should be able to seek funds from the trust, and stakeholders should vote on who becomes a beneficiary. By creating a discussion about who should be financed, the process produces a positive feedback loop like those found in other cryptocurrencies with governance systems, such as Dash. Healthy dialogue ensures that the community is always assessing and arguing its views ahead of crucial decisions.

Long running and, in many instances, unresolved disagreements about the technical and moral direction of the codebase have plagued Bitcoin with its block size debate, Ethereum with the DAO split, and a slew of other cryptocurrencies. Many of these conflicts, as well as the splitting of the community that occurs when action is taken, can be attributed to the absence of any mechanism for implementing change.

Looking to lessons from the past, Bitcoin’s adoption of (SegWit) Segregated Witness could have been handled a lot better. Did the DAO attack really have to result in the hard fork on Ethereum? Could it have been managed better so there was not such a dramatic community breakdown?

In the worst-case scenario, moral authority to act might simply devolve to whomever has the developers, infrastructure links, and money, rather than the community’s best interests. It’s difficult to gauge if actions are valid if a major segment of the community is unavailable, or disengaged owing to poor incentives.

Some cryptocurrencies like Tezos have a model where the cryptocurrency protocol is handled as a constitution, with three parts (Transaction, Consensus, and Network) and a set of explicit rules and procedures for updating the constitution. However, there is still a lot of work to be done on incentives and how to represent and update a crypto protocol using a formal language.

IOG have been researching governance in crypto for years. They have written papers as far back as 2017 on proposing a treasury for Ethereum Classic. Another paper, authored out of Lancaster University, focused on the concept of a treasury system and a viable, democratic method to long-term development financing for Cardano.

Formal methods, machine comprehensible specifications, and combining a treasury with this process for financial incentives are just some of the solutions IOG pursued. Looking back now, it’s clear they were putting the chess pieces in place, to create the apparatus necessary for the Age of Voltaire vision presented at ScotFest in November 2022. More on this later. 
Cardano Improvement Proposals (CIPs)
One of the early governance pieces implemented in November 2020 was CIP 0001, which explains what a CIP is. Anyone who has ideas for enhancing Cardano may present them in the form of CIPs (Cardano improvement proposals). CIPs are a means of formally proposing enhancements in a consensus-based manner. They are an essential component of Cardano governance, even though they are not binding, nor a requirement for treasury or protocol modifications. 

Technically, the first ever CIP was created in October 2019 and subsequently became CIP-1852. It extends BIP44 and was written to document how Cardano wallets handle keys and addresses. This document existed even before the CIP process was created. It was named CIP-1852 by Sebastien Guillemot after the year Ada Lovelace died (her birth year, 1815, is used in the cointype field). 

A CIP follows a standard format: the proposal structure is templated to make debate and evaluation easier. This allows other members of the community to weigh in on improvement recommendations, or issues in a proposal. CIPs are kept as text files in a versioned GitHub repo, and their revision history provides the proposal's historical record. For those who aren’t on GitHub, cips.cardano.org is an auto-generated sister site maintained by the Cardano Foundation.

Every CIP has the following format: Preamble, Abstract, Motivation, Specification, Rationale, Path to Active, Copyright. The concept is developed as a written proposal and submitted as a pull request to the CIP repository after initial discussion and feedback. The updated Draft CIP is then publicly processed in the following manner:


Figure 10.1: CIP workflow from CIP0001

CIPs are processed in a semi-formal manner: Editors of CIP proposals meet on a regular basis to discuss and assess ideas. Meeting minutes are available to the public, and meetings are held every two weeks. Authors are encouraged to contribute and offer comments, and discussions often take place simultaneously in the Cardano forum CIPs section and/or in the GitHub pull requests. If you have designs on becoming a CIP editor, you should read Robert Phair’s blog about his experience in the role.

Consider the CIP repository to be a collection of useful tools - some may play well together, while others will not. You have complete control over which CIPs your implementation adheres to. The community will lean toward some more than others, new ones should be submitted as Cardano grows.





Figure 10.2: CIP workflow from editors’ perspective
What is Project Catalyst?
Another governance piece introduced in 2020 was Project Catalyst. Catalyst is a grant program that combines proposal and voting processes. Establishing a long-term future for Cardano growth began with a treasury and democratic voting. 

Catalyst is a community-driven innovation grants program that uses elements of decentralized governance to make certain decisions (i.e. the Cardano community votes to decide which proposals should receive grant funding). Funds are granted as ada, provided to IOG directly from the Cardano treasury, to administer the funding disbursements. To recap, the treasury is replenished through a combination of:

Transaction fees: a small fee is collected from each transaction processed on Cardano
Reserve funds:  portion of its initial supply of ada was allocated to a reserve, meant for long-term funding for the ecosystem. 

There are effectively two parts to Catalyst:

1. Submitting, reviewing, and voting on proposals
2. Delivering the grant-funded project and demonstrating proof of achievement as part of the community-led accountability model

So in this way, members of the Cardano community submit proposals to deliver projects for the benefit of growing the Cardano ecosystem. The community then reviews the project proposals, providing feedback based on criteria of ‘Impact’, ‘Feasibility’, and ‘Value for Money'. Finally the community then votes on which proposals to allocate funding towards. Catalyst currently uses IdeaScale to crowdsource all proposal submissions and community reviews. ProjectCatalyst.io is where all of the funded-projects progress reporting and accountability is ultimately open and available for community members to keep track of. 






Figure 10.3:  The opening screen for each Catalyst Town Hall meeting


Decision making process

Scientists (even nuclear physicists ), developers, executive types, investors, and the general public are among the ada holders who vote. With such a diverse field of participants, with different agendas and motives, there must be proper mechanisms in place to preserve inclusivity, and ensure fair reviews and voting takes place. 

A person’s voting power is proportional to the quantity of ada they hold; the more ada they own, the more weight their vote carries. Along with direct ‘yes’ voting, a person might transfer their voting authority to an expert they trust as part of the liquid democracy concept. In this instance, the expert votes on behalf of their delegators. Note that ‘No’ voting was removed in Fund11.

Following the vote, project ideas may be assessed and ranked depending on the number of yes/no votes; the poorest project proposals will be eliminated. The top-ranked ideas will be financed in turn until the allocated treasury money is depleted, after which the shortlisted proposals will be ranked according to their score. Breaking down the decision-making process into phases ensures each proposal is rigorously and fairly critiqued.

IOG’s research team leveraged ZK proofs to safeguard voter privacy. Zero-knowledge (ZK) approaches are mathematical methods for verifying information without exposing any underlying facts. The zero-knowledge proof in this situation indicates that someone may vote without providing any personal information other than their eligibility to vote. Any prospect of voter coercion is eliminated as a result. 

Project Catalyst is a treasury system that combines proposals, and voting processes, with the goal of fostering a democratic culture in the Cardano community. Cardano’s treasury will initially be replenished by a proportion of stake pool payouts, assuring a long-term treasury supply. Other blockchains have treasury systems, but IOG’s combines perfect anonymity thanks to zero-knowledge proofs, liquid democracy thanks to expert engagement and vote delegation (planned for Catalyst in future), and community participation.

It’s also worth noting that this treasury system technique may be used on blockchains other than Cardano. It has previously been suggested that it be implemented for Ethereum Classic and we’ll see later how COTI availed of the Catalyst Natives feature. 

Following a successful limited user group trial, Project Catalyst became accessible to the public. Although Cardano on-chain governance is still in its infancy, all metrics and indicators point to a bright future with the community leading the way. 


Figure 10.4:  Catalyst overview

There are a lot of moving parts to Catalyst. This graphic from IOG’s blog post Project Catalyst - A virtuous cycle of Cardano ecosystem development is a good summary of the steps involved and end goals. 
Catalyst’s early funds 
In Sept 2020, IOG announced the establishment of Project Catalyst’s first public fund, a milestone for Cardano in terms of on-chain governance, treasury, and community innovation.

The public fund was launched after five months of intensive activity across two earlier pilot funds. The first experiment, dubbed ‘Fund 0,’ was conducted with the help of a focus group. Fund1 was the first time the concept was shared with the Cardano community, enlisting the aid of over 50 people to help IOG construct the platform and procedures. While this voting round did not provide ‘real’ financing, it was a significant opportunity for the Cardano community to test and enhance the new process.

There was a long way to go. If Fund0 was the technical run through, then Fund1 was the dress rehearsal. Fund2, which was announced in September 2020, was the opening night when the community’s top performers fought for financing to bring their concept to fruition.

Funding great proposals

A pioneer group of 50 community members assisted IOG in identifying areas for improvement so that they could build and enhance the process before making it more broadly available. Clarifying the documentation and standards encouraged community members to participate more and submit proposals. 

To that end, IOG worked on a guide to assist anybody in creating their best proposal possible for Fund2 and beyond. The community could access up to $250k worth of ada in the first public fund. 

Starting small, the community were asked to respond to a challenge statement: ‘How can we encourage developers and entrepreneurs to create dApps and businesses on top of Cardano in the next six months?’ Funding proposals could address this with a broad range of concepts, including marketing campaigns and infrastructure development, as well as business planning and content production.

The first step was to ‘examine the problem,’ which included asking members of the community for their input. Then, through a special Telegram chat channel, IOG urged everyone to submit their ideas to the innovation platform, where they could collaborate and debate.

The public votes

It was put to a vote after the phases of brainstorming, cooperation, and proposal. Proposals were evaluated on IdeaScale, or via a mobile voting application. When it came time to vote, everyone registered using the voting app. Each participant’s ‘right’ to vote is connected to their ada holdings, and voting earned them further ada rewards. Voting works similarly to a ‘transaction,’ enabling all participants to cast a vote to say ‘yes’ or ‘no.’ 

How it works

Voltaire is a critical component of the Cardano ecosystem since it enables every ada holder to participate in decision making about the platform’s future development and contribute to the ecosystem’s growth. Project Catalyst is a critical first step in achieving such capacity.





Figure 10.5: Catalyst ‘here’s how it works’

Fund3 went live in January 2021, and with each fund, IOG wanted to grow the Catalyst community by encouraging more individuals to participate. Every funding round starts with a set of objectives. Each challenge symbolizes the Cardano community’s ‘intention,’ a common objective to accomplish. IOG likes to speak about ‘return on intention’ as a means of monitoring project success. Each challenge is intended to be wide enough to elicit both technical and general ideas while remaining focused. 

Fund2 had a $250,000 ada pool, while Fund3 doubled that, awarding $500,000 in ada to proposers, voters, and community advisors. The breadth, amount of money, and community participation have all increased with each funding cycle. On the IdeaScale innovation platform in Feb 2021, there were 7,000 members and 1,800 active voters. Adoption was increasing by 10% per week.

Fund4 was the most accessible and ambitious round yet, as well as the first million-dollar round — the ada pot used to finance Cardano development initiatives. The funding was used by proposal teams to create tools, construct dApps, establish developer education and training efforts, and much more. 

Voter registration increased considerably. The redesigned registration center was now completely connected with the Daedalus wallet. Yoroi lite wallet users could easily register via a browser plugin. After that, voters could finish the process using a specific mobile voting app, which can be downloaded on iOS or Android. Project Catalyst had risen to become the world’s biggest decentralized autonomous organization (DAO) in less than six months.
Catalyst Circle 
As Fund4 came to an end in July 2021, Catalyst had already proven itself as a one-stop hub for teamwork and decentralized innovation. However, this rapid expansion brought with it new obstacles. 

Project Catalyst was gaining in contributions from increasingly different functional groups who were helping to bring the collective intelligence forward. Specifically, community advisors, funded-proposers, stake pool operators (SPOs), toolmakers & maintainers, all who contribute to Catalyst’s success and expansion.

Project Catalyst gains from having a broader set of participants as it results in more diverse ideas and proposals. It also makes communication between all of these groups more difficult. Every cohort wants to be heard, and their thoughts and concerns need to be aired at the project level.

These groups need representation and trustworthy leadership to advocate for them. This is why the Catalyst Circle was created. Catalyst Circle was a ‘human sensor array’ that served as a representative body for all the Project Catalyst participants. The Circle kept track of Catalyst’s present state and future intentions for governance. Within the Catalyst ecosystem, it identified and discussed issues, objections, and possibilities. For example, the Circle might debate the amounts distributed to a fund, tweaks or conditions to incentive parameters, the Catalyst API, and so on.

This activity gave an insight into the hopes, desires, needs, and worries of the community inside Project Catalyst by documenting meetings and collecting activities in a backlog available to everyone. The Circle was also in charge of choosing its own future form and designing the Circle election procedures. Catalyst Circle was paused after V4. It will likely restart, or resurface in a new form, with the learnings and experiences key to any future incarnations.  
Catalyst Natives 
As part of Project Catalyst, the first Catalyst Natives pilot was launched in late 2021. Catalyst Natives allows any project to tap into the collective intelligence of the community to solve business challenges and outsource projects. Catalyst Natives gives decentralized innovation fund management to partners, some external to Cardano, aiming to develop their ecosystem by incentivizing innovators to assist in finding solutions to problems.

COTI, the first Catalyst Native

Catalyst Natives expands access to Project Catalyst to organizations outside of the Cardano ecosystem could now present challenges and give incentives and rewards to individuals who successfully satisfy the challenge with their suggested innovations.

COTI presented the community with a novel technological challenge in this pilot, which was to create an innovative plug-in to be integrated with their existing ADA Pay system to support all the different e-commerce software solutions. 

Following the pilot, IOG allowed Catalyst Natives to accept more challenges from other entities; however, these challenges were selected by IOG, in the first phase, to ensure they provide value to the Cardano ecosystem. Organizations proposing challenges via Natives will finance those ideas, thus Catalyst Natives will not utilize Cardano Treasury funds to pay for the initiatives that have been successfully voted on. COTI distributed $100k in COTI tokens in Fund7, which was in addition to the $8m ada fund.

Catalyst Natives is an opportunity for businesses of all sizes to have access to a vault of ideas and the people who can help them come to life. Catalyst Natives is now aiming to assist Cardano ecosystem partners, and native asset token projects, handle particular pain points for which they either do not have the resources, or simply do not have a solution, and outsource them as Catalyst challenges for proposers to solve. 
Later Funds
Every Catalyst fund cycle has provided new, remarkable accomplishments. Fund7 was no different. 

Figure 10.6: Fund7 stats

After the votes were tabulated and counted in Fund7, 269 additional initiatives were selected to get ada. Given that each of these projects was created in response to 24 real-world problems provided by the Cardano community, as well as one additional task issued by COTI, Cardano’s first Catalyst Native pioneer, these were impressive numbers. 

This time around, over 52,500 wallets registered to vote, and community advisers reviewed over 900 proposals to assist voters make informed judgements. The number of ideas financed by the Cardano Treasury had almost quadrupled in a short period of time, reaching 575 projects. 

The Cardano Treasury now contained roughly 800m ada in order to maintain and build the ecosystem. Many of the projects that were funded in previous rounds have now been completed and their end products were being showcased.

Fund8

Every three months, a new Project Catalyst innovation fund campaign launches, offering the chance to obtain resources from the Cardano Treasury. Fund8 offered $16m funding in ada.

Fund8 results confirmed the momentum just keeps growing as voting turnout increased and a diverse range of projects were funded. One of the smallest amounts requested, and funded, was also one of the most significant. Sebastien Guillemot’s successful proposal meant he was the first CIP editor to be paid for his time. More editors followed, serving as stewards of the CIP process. 

Catalyst also partnered with the Financial Times and Seedstars (seedstars.com) to launch the FT x Cardano Blockchain Challenge where selected startups participated in a 3-day Bootcamp and connected to Seedstars’ network of mentors. 24 startups were selected to participate in a 3-month Acceleration Program.’ More details are on Seedstar’s website.

April 21, 2019… Who pays? Who decides? CH:

This is why it’s so incredibly important that you have a treasury system …and voting systems because right now here’s how the cryptocurrency space works and this is why things get so toxic ….you have a very small group of people who are developers, investors, big people who are actually building stuff in the space, the entrepreneurial class, developer class the infrastructure class… then you have the speculators which are everybody else …and they hold the currency, they’re fans of it, maybe even philosophically aligned with it …but they don’t have a voice, they can’t do anything …they’re just sitting there just hoping for things to materialize.

….and then a subset of them maybe move into the other class when they have smart contracts or whatever… but the vast majority of them are there yet they have opinions about where things should go…what they should do …and so the key is to give them tools to organize… tools to vote… tools to discuss the philosophy and direction …to have teeth, not just ‘here’s my opinion’, but also when my opinion is let manifest and gets a democratic consent behind it …then that opinion will turn into money …that then can be used by the other class.

All of a sudden everybody has power and actually has a voice ..and an opinion and you’re not just talking about when is this coming out, or what is is it that is coming out…you’re actually talking about where do we want to go, and how are we going to get there and the things we need to do to get there… who’s the best leader to get there… you can’t fork that…. you can fork the code and have another Treasury system…but it’s like saying well that big meetup group over there… I’m going to host my own meetup group and I’m going to copy everything… the same banners and the same catering and the same everything… it doesn’t mean other people are going to show up 


The Cardano cFund
The cFund, which was first unveiled at the 2020 Shelley summit, is an early-stage investment fund that focuses on creative firms on Cardano. Wave Financial, in collaboration with IOG, manages the cFund, a crypto-native hedge fund. The fund uses an early-stage venture approach to invest in creative technological firms that are building Cardano-based apps, services, and products, as well as other R&D projects that IOG is working on.

The ‘c’ in cFund

The letter ‘c’ in the name relates to the mathematics word ‘coefficient,’ which refers to a variable’s multiplier. cFund is positioned to provide a multiplier effect in terms of growth and reach for its portfolio firms by using both IOG’s and Wave Financial’s subject knowledge and industry relationships.

Services offered

The cFund serves as a funding provider, adviser, and partner to its portfolio firms and the greater Cardano ecosystem. cFund delivers access and direction to its portfolio by using IOG and Wave Financial resources, reputation, knowledge, and network. 

According to IOG’s foundational philosophy of ‘cascading disruption, most of the structures that make up global financial, governance, and social systems are inherently unstable, and slight disturbances may generate a ripple effect that radically reconfigures the system. The purpose of cFund is to find and fund solutions that bring these disparities together in a fair and transparent way for all participants. While other cryptocurrencies have strong ties to Silicon Valley, Cardano is innovating with Catalyst acting as its own ‘built in’ funding mechanism.

COTI, a decentralized and scalable payments network for the e-commerce sector, was cFund’s first investment in this area. 

October 16, 2020. …. There are a lot of different funds so could you explain to us what is DC fund, cFund and the Cardano Foundation fund? CH:

So, the DC fund is what we’ve termed the funds that are coming out of Catalyst… and those are grant models … Cardano doesn’t have agency, so we can’t own land, it can’t have intellectual property… it can’t have equity, these types of things …so when it gives out funding… It's like when the National science foundation (NSF) gives out funding, or DARPA gives out funding …where it’s funding the development of something because we, as a society, have determined that that is a good idea. 

So, for example when NSF gives research for theoretical physics …it says we, as a society, would like our brilliant physicist to be well funded so that they can figure out how time works and gravity works and so forth …but there’s no money that comes out of that …or these things but there’s a social benefit, that potentially could be leveraged over time to make the country better… Perhaps we invent anti-gravity at some point …. but it’s not the primary goal. 

So, we look at DC fund like that …. where we say it’s a ‘return on intention’. Grants are coming through, and the goal is to make Cardano better…. but it’s not to make Bob a millionaire, or something like that… 

cFund is a venture capital arm of my company and Waves… we’re working together and setting all of that up and basically that’s going to be where you run a project and you come to Charles and the others who are involved with that… you say, ‘I would like you to invest in my company… and give me the resources I need to get it to the next level…. and then we would look at you like any venture capitalist would look at you…. ask you the same questions Andreessen Horowitz (a16z.com) will ask you, or Kleiner Perkins (kleinerperkins.com) will ask you and so forth …and if we determine it’s a good investment, I’ll open up the checkbook and cut a check and send your way and we get equity back for that, because that’s a private investment.

Then the Cardano Foundation they have something called the CCCI, Commercially Critical Cardano Infrastructure… and that’s saying there needs to be some product validation and bootstrapping, that Cardano really is competitive, or capable of doing the things that Ethereum and EOS and Tezos and Algorand do. 

So we’re going to give out some very specific very targeted grants to help get the ecosystem along …okay the DC Fund, the community is in charge of that … the grants from the (Cardano) Foundation, the Foundation’s in charge of that and they’re very directed towards catching us up and getting us where we need to go to compete with Ethereum and the rest of the gang …and the cFund is a good old-fashioned investment for things that I think we ought to have on our ecosystem.
dReps
IOG introduced the notion of delegating your voting rights to a Delegate Representatives (dReps), and urged people interested to register during a Fund8 Project Catalyst Town Hall. 

The ongoing growth of the Cardano ecosystem is great news but, on the other hand, offers a problem. The community’s obligation to examine and vote on ideas grows as the quantity of proposals grows. A new approach was needed to guarantee that all ideas get the attention they deserve.

Ada holders may give their votes to one or more dReps through delegation. This provides the more passive voter with a chance to have their voice heard, but now across a larger number of proposals than they could read and evaluate personally.

Catalyst dReps will vote on most Project Catalyst proposals, improving the quality of decision-making within each Fund. dReps will collaborate to develop policy, gather and evaluate data, consult with experts, and ultimately vote on a variety of initiatives and issues proposed by the community. If you’d like to get involved, you can join the dRep pioneers here.  

Fund9

Catalyst’s relentless, Borg-like momentum continued with Fund9 opening in June 2022. There is typically something new and innovative with the arrival of each fund, and this time Cardashift joined the Catalyst Natives program. Their challenge was based on value creation through positive impact-oriented projects. Cardashift listed Cardano’s ‘green’ credentials, its focus on Africa and its deterministic nature among their reasons for partnering with Catalyst in their medium blog post. As with every quarterly fund, the rewards for successful proposals increased. The Fund9 launch guide outlined how the 16m ada was to be allocated. 
Tactical Pause for Catalyst

Although Catalyst has been a huge success in many ways, it’s not perfect. There were also questions asked of Fund6 winner Cardax DEX after launching on Milkomeda (dcSpark’s Cardano sidechain) instead of Cardano mainchain as initially proposed. There were rumblings of discontent when one the 205 winners of Fund9 was a controversial proposal called Daedalus Turbo.  The problem statement of the proposal read: 

Daedalus, the decentralized Cardano wallet, is painfully slow, taking a whole day to sync initially and hours to resync when used only occasionally—an unfavorable impression of Cardano for new users. 



Many Cardano users felt aggrieved as the sum rewarded was large, with other projects missing out. Anyone conducting a basic ‘gap analysis,’ as SPO Rick McCracken tweeted, would probably arrive at the same conclusion that the project was not timely as years of research and product development were already devoted to Mithril. For anyone following Cardano, IOG’s Lace (lace.io) light wallet has been prioritized over Daedalus for some time.  

From a user experience perspective, many people felt overwhelmed trying to track over a thousand proposals for a given fund on IdeaScale. Many promising projects have gone unfunded. It was generally welcomed by the community when IOG announced a ‘time out’ for Catalyst in a November 2022 blog post.  

As Catalyst took a break, there was a timely SoK research paper published just around this same time, reflecting on the state of governance in ten blockchains including Bitcoin, Ethereum and Cardano.

The paper lists seven properties by which to assess different requirements for effective blockchain governance. 

Suffrage deals with participation eligibility, how inclusive is the governance mechanism? 
Confidentiality: are decision-makers’ inputs protected from ‘external influences’? 
Verifiability: can decision-makers confirm their input has been considered in the output?
Accountability relates to decision-makers being held accountable for their input
Sustainability questions if decision-makers are suitably incentivised?
Pareto efficiency asks ‘how well the intentions of the decision-makers can be turned into actions?’
Liveness is a measure of how quickly a blockchain’s governance mechanism can produce outputs efficiently



Figure 10.7: The partition map of governance properties from the ‘SoK: Blockchain Governance’ paper

The paper concludes that while each blockchain displays some of the properties, no blockchain meets all the requirements for effective governance. It was food for thought just before the dawn of the Age of Voltaire. 

With the Catalyst pause after Fund9 and the Age of Voltaire still in its infancy, the Catalyst team introduced a new concept in the first Town Hall of 2023 called Special Voting Events (SVE) that leveraged Catalyst tooling. A SVE was a vote held that was unrelated to Catalyst fund cycles. It was a stopgap measure for obtaining community consent on important decisions before Catalyst resumed with Fund10 and new governance tools were being built to allow for polls and temperature checks. We learned in ScotFest 2022 presentations that Catalyst is merely a sighter for the Age of Voltaire, and 2023 would be about integrating tooling to ultimately facilitate the implementation of CIP 1694 which we will discuss shortly. 

Fund10 

Catalyst made a welcome return with Fund10 in June 2023. The updates and changes were announced in a blog post. Catalyst’s Lead Architect, Stephen Johnson, walked through the details and demoed how the community could now start to interact with the ‘Catalyst continuous testnet’. 

Up until Fund10, Catalyst was implemented as a mix of on-chain and off-chain components. Proposals lived on IdeaScale, supported by android and iphone voting apps and a dependence on the re-purposed Jormungandr node (previously used for the Incentivized Testnet). As the Voltaire era unfolds, the voting experience has moved into the growing list of light wallets, complemented by a new website, projectcatalyst.io.

Fund10 saw 192 projects, from 100 unique proposers, receive a total of 50 million ADA in funding from the Cardano community. After the pause, deep in a bear market, ada holders were clearly hungry for Catalyst’s resumption with approximately 409,000 votes cast, a 12.48% increase compared to Fund9. 

The most significant moment of Fund10 was that it was the first time the community could decide who should be in charge of Catalyst. The community voted for IOG to continue to provide services to the community as the Catalyst Fund Operator. The Catalyst team’s proposal is to replace IdeaScale with ‘Catalyst Voices’. Michael Madoff, the Group Product Manager for Voltaire, joined Kriss Baird (Group Product Manager) for Town Hall  #140 to explain how Catalyst fits in the overall Voltaire roadmap era. Madoff explained:

‘We learned a lot about experiments with Community governance through everything that's happened in Catalyst and the contributions everyone here has made’ 

There was pushback from some proposers, for example on Twitter (X),  PACE posted: ‘This is a massive concern as IOG has a direct incentive to remove competition from categories they are competing in’. There was also an article highlighting that a very small fraction of the community has disproportionately large voting power and that up to 50% of wallet holders have virtually no influence, controlling only 1% of the voting power. 

Some suggested Quadratic Voting could address this issue, while others rejected the suggestion. Adam Rusch posted his views that Quadratic Voting is not a silver bullet for Governance on Cardano Forum. 
Each project team was now obliged to provide more transparency by formulating their 'Statement of Milestones,' using the Milestone Module, which monitors critical checkpoints throughout the project’s lifecycle.
Projectcatalyst.io also had a full data refresh updating with all the Fund10 cohort data. This enabled users to track the progress of each funded project within the milestone program. LIDO NATION had previously blogged that “the hardest part of providing the Catalyst Explorer has been getting the data.” 

Fund11

Updates to Fund11 were announced at the Dubai Cardano Summit in November 2023. Many of the changes addressed feedback from the community. The ‘downvote’ made a welcome exit, a cap of five proposals per person was introduced and proposers could not have anything projects open from Fund7 or earlier. Fund11 saw the following three categories:
Concept: for brand new ideas limited to a budget of 100K ada.
Solution: projects who already have at least a proof of concept for review, limited to 300K ada.
Product:  proposals with a product already in the market, limited to 750K ada.
…each category had distinct tracks to focus the scope of submissions: 
Cardano Use Cases
Cardano Open: Developers
Cardano Open: Ecosystem
Catalyst Systems Improvements: Discovery
Catalyst System Improvements: Development

Daniel Ribar (Community and Product at Project Catalyst) talked in depth about Fund11 in a Cardano with Paul interview. With the longtime Catalyst leadership team now voted in for another year to run affairs, the team clarified that they will apply fund rules. Proposals submitted incorrectly, in the wrong track or out of scope, will be notified with guidance on how to come inline, otherwise they risk being withdrawn. 

There is plenty of feedback and suggestions coming from the community. For example, Santiago Carmuega, of TxPipe, explained his case for an alternative parameter that would be more effective than max number of proposals per team. Small details can have a big impact on a business model of small teams following an open-source software philosophy. Founder of Axo, Jarek Hirniak felt Catalyst needs to be more open to ‘bold experiments’. 
Working Groups
Working Groups is an initiative to address something that’s been missing from Catalyst since the start, an effective way to crowdsource community input when deciding on changes to funding rounds. The proposal is for small teams to run their own Working Groups anywhere in the world, in-person or online. Each group must concentrate on one of three categories:

Catalyst Strategic funding priorities Working Group considers use cases already funded and new high-value areas that may benefit from funding. 
Catalyst Operating Parameters Working Group considers how future funding could be allocated and if any Catalyst operating parameters could be updated.
Catalyst-Funded Project Incubation and Acceleration Working Group focuses on high potential Catalyst-funded startup ideas by exposing them to a global network of angel investors and accelerator programs.

The Catalyst working groups initiative provides communities the chance to engage with other Cardano communities globally or online. See the full schedule of events for your local event.
Fund12
The community decided the official launch location for Fund12 with a 1-wallet-1 vote. Barcelona was chosen for the boisterous gathering which was also streamed live. Although the Cardano Foundation had participated in funds as far back as Fund4, Frederick Gregaard communicated in his keynote that the CF would be taking a more active role in Catalyst going forward.

1,283 proposals were submitted for Fund12. You can review the latest stats on the ‘Funds Overview’ page on projectcatalyst.io. Each funded project is onboarded and must follow an accountability framework, where they draw up their statement of milestones (SoM) which must be approved to receive any funding. The statements of milestones serve as a public roadmap for Proof of Achievement (PoA). There is also a community-led accountability program and Proof of Life verifiers who monitor all grantees.

The official Fund12 launch guide outlining some new categories, notably the Cardano Partners and Real World Integrations cohort. The voting stats for Fund12 voting were: 
Over 5,000 unique wallets were involved 
More than 200,000 individual votes were cast
Over 1.5bn ada was used for voting.
Fund12 results included 258 new projects and Catalyst reached a milestone of over 900 completed projects, allocating more than 100 million ada in funds.
Accountability
Project Catalyst introduced several mechanisms to ensure stricter accountability in 2024. There was the first iteration of a formal cancellation policy that informs projects when a change of scope or adjustments on their deliverables is necessary. Some of these projects will inevitably be sunsetted. It’s to be expected in an experimental, start-up process. 

A new community review process was also introduced, allowing anyone to provide oversight based on set criteria. The goal is to aid the proposers to create quality submissions and steer voters attention to worthwhile proposals.

Hermes & Athena

Throughout 2024, the Project Catalyst team delivered Milestones in the Hermes and Athena projects. The hotly-anticipated final deliverables include a high-availability blockchain voting database (Hermes) and a hyper-lite accessible voting DApp, replacing IdeaScale and current mobile app. Both are being developed under an Apache-2 open source licence. 

Catalyst Voices 

Development continued on Catalyst Voices, the replacement for Ideascale outlined in their successful Fund10 proposal. The plan is to phase out IdeaScale in 2025.

In addition, a separate proposal funded in Fund11, regarding alternative voting schemes based on protocols proposed by IO Research, Photrek, and the Catalyst team reached its third milestone. 

The Catalyst team also released their Catalyst Horizons report documenting various milestones. 
Fund13: Apocalypse DAO
Fund13 kicked off, as usual, with a launch guide containing all the relevant dates and instructions. FC Barcelona, Brave Browser, and TechStars were among a star-studded list in the Partners and Real World Integration category for Fund13. The shortlist was finalised by 13 individuals representing the Intersect Committees and its working group members. Of these, 10 members participated in the shortlist workshop, where proposals were carefully evaluated based on documented criteria:
Transaction Volume Potential
Budget and Fiscal Prudence 
Brand Size and Potential
Project Maturity and Stakeholder Agreements 
Geographic Diversity
Balanced Value Addition
Diversity in Marketing Approaches
Top-Tier Venture and Acceleration Proposals
Clear Milestones and Deliverables

The moderation phase for community reviews concluded with total reviews reaching an impressive 56,592, highlighting how engaged the community are with Catalyst. The Catalyst team organized a Pitch Fest for candidates to showcase Fund13 ideas in two-minute elevator pitches, live streamed on X (twitter). 
There was much furore and debate following the Fund13 results, specifically about how the CF’s 180m ada voting stake was used. Despite many dismissing X (twitter) as the wrong place for discussions, it remained the primary forum on which many vented their feelings. 

The CF released several blog posts about their involvement in Fund13 where they told us what they were going to do, did it, and then told us what they did. Their process of having 30+ reviewers inspect and filter 1,800 proposals was explained for transparency. The criteria for selection was based on the previously shared principles in Our Cardano.

It had been flagged for some time that a large ‘whale’ could intentionally, or unintentionally, create waves that sink relatively smaller vessels. For example, in an essay titled Cardano Improvement Proposal — 1694: Can Decentralized Communities Make Superior Decisions? authors Kenric Nelson, Juana Attieh, Megan Hess, Vanessa Cardui, and Stephen Whitenstall evaluated Cardano’s shift to a community-led governance model. The recurring issue of unfair distribution of voting power was raised. The essay warned a system with a one-coin-one-vote (1c1v) philosophy can result in a plutocracy, with a small portion of addresses tend to control a disproportionate amount of voting influence.

This is a bigger risk when participation remains low. It’s important to note the registered stake eligible to vote at 4.8 billion ada from a possible 35 billion. The CF’s stake was 3.75% of this registered ada and just 0.5% of the total supply of circulating ada. The CF compiled an FAQ forum post including:

9. Why do you think you should get to vote with the ada you own?
The Cardano community has adopted a governance model that is evident in all constitution proposals, including the Intersect constitution draft, which is based on “one lovelace, one vote.” As the only not-for-profit actor whose entire statutory purpose is the success of Cardano, we believe it is our responsibility to be a constructive participant in the Cardano governance ecosystem. Neglecting this role would mean failing to fulfill our statutory purpose.
Kriss Baird provided analysis of Fund13 results promising solutions to centralization concerns and governance gaps. The analysis involving ‘taking CF's VP, slashing it, and removing it altogether to compare the results’ was the first time a participant's input was singled out and scrutinized. If any participant is restricted or removed by the entity running the process, it would seem to stray from the basic concept of how a Decentralized Autonomous Organisation should function. Such a move by the Catalyst team would also seem to contravene several of their own stated 11 blockchain tenets.
T4 - Everyone’s inputs and contributions to the system will be recognized, recorded, processed and assessed fairly. 
T5 - The value and data users contribute and/or create will not be locked or processed without their consent.

For balance, it’s important to note there were proposals funded which didn’t attract the CF’s vote. Notable among them was Sheldon Hunt’s Institutional-Grade Layer-2 for Bitcoin DeFi on Cardano, in collaboration with BitcoinOS, Tesseract and More proposal. The CF’s vote in Fund13 resulted in an increase in the number of funded proposals, as well as a wider geographic spread. Most of the successful proposals from Africa were as a direct result of attracting the CF’s vote.   

If the CF is the only entity scrutinized because their stake is deemed disproportionate compared to a low participation rate, then what is the plan for larger whales when greater treasury sums are in play during a bull market? It’s not clear how this conundrum will play out. How one implements voting limits, checks and balances to a permissionless DAO will require some careful thought.

Should Fund13 be seen as a warning shot, ada holders should be concerned with what is seated in the chamber now. When the Plomin hard fork gun went off, 1.5 billion ada came into play and we’ll be going to the polls with ‘one lovelace, one vote’. The Catalyst team has been preparing for improvements for some time however. Daniel Ribar outlined in an X post some of what to expect in 2025. 

Quadratic voting and other advanced methods have been investigated to counter the unwelcome impact of 'whales' shaping consensus. The Catalyst team partnered with IOG Research and Photrek to publish a report analyzing five different approaches to quadratic voting. Well-known weaknesses of quadratic voting such as collusion attacks were also carefully considered. 

Participating in Catalyst

There are several ways to participate in Project Catalyst. Submit a proposal, vote, review, comment or become a mentor. Registering an account on the collaboration platform is the first step. Another option is to join the Project Catalyst community at TownHall every Wednesday, which is live broadcast on IOG’s YouTube Channel. You can monitor each fund and catch up on previously funded proposals on projectcatalyst.io, or alternatively with LIDO NATION’s excellent Catalyst Explorer.
