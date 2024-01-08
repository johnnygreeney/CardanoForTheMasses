# Chapter 3: Proof of Stake

*‘He who has a why to live for can bear almost any how’* ― Friedrich Nietzsche

## What is proof of stake?

Proof of stake (PoS) is a consensus protocol, or methodology, that determines consensus based on the amount of stake (or value) retained in the system. A consensus protocol, in essence, is what governs the laws and parameters that regulate the behavior of blockchains, similar to a set of rules that each network member follows. Because blockchains aren’t controlled by a single, central authority, a consensus protocol is employed to enable dispersed network users to agree on the network’s history as recorded on the blockchain - to achieve agreement on what’s occurred and move forward from a single source of truth.

Cardano is based on Ouroboros, an innovative proof-of-stake consensus system that was created via peer-reviewed research. Stake pools, which are server nodes maintained by a stake pool operator (SPO) to whom ada holders may delegate their stake, are at the core of this PoS technology. Stake pools are used to guarantee that everyone may participate in the protocol, regardless of technical expertise or availability to maintain a node. These stake pools are focused on upkeep and hold the pooled stakes of several stakeholders in one place.

**Proof of stake vs proof of work**

Proof of work (PoW), on the other hand, is a synchronous system[^1] that encourages miners to compete to solve problems inside the block first. This problem-solving is rewarded via a system of incentives. This strategy, however, comes at a cost: higher power consumption and longer time span to handle issues within the chain. These issues might cause the network to slow down dramatically, making it expensive to maintain.

One of the most important elements of proof of stake (PoS) is that as a user’s funds grow, so does their ability to maintain the ledger. ie. the ability to create new blocks that can be put to the blockchain and timestamped correctly. A mix of random selection and a determination of their stake, or money, determines who creates a new block. Within the chain, a form of leader election takes place. Under a proof-of-stake system, users earn transaction fees as they go, increasing their balance with passive income (staking). This strategy promotes the blockchain’s steady and consistent expansion in line with the goal of the network becoming stronger as participants join. 

**Benefits of proof of stake**

The following are some of the main benefits of PoS versus PoW:

- A proof-of-stake protocol incorporates stringent security procedures
- Decentralization - the danger of centralization is lowered by imposing penalties for selfish behavior inside the network 
- Energy efficiency - energy consumption is incredibly efficient since the blockchain requires less power and hardware resources to operate. For example, ‘Berry’ is a Cardano Stake pool[^2] running on a Raspberry Pi.[^3] Markus Gufler[^4] ran a Cardano node on a Rock Pi (single-board computer made by Radxa) at the IOHK Summit in 2019. A Rock Pi uses as little as 10W to function. 
- Cost-effectiveness - proof-of-stake currencies are considerably more cost-effective than proof-of-work currencies.

Although using proof of stake for a cryptocurrency was a contentious design decision, IOG chose to embrace it since it offers a method for introducing safe voting, has more scaling capacity, and allows for more complex incentive schemes.

The Ouroboros protocol was developed by a skilled group of cryptographers from five academic institutions headed by Professor Aggelos Kiayias of the University of Edinburgh. Beyond being verified secure using a rigorous cryptographic model, the fundamental innovation it delivers is a modular and adaptable architecture that allows for the combination of multiple protocols to boost functionality.

Delegation, sidechains, subscribable checkpoints, improved data structures for light wallets,[^5] multiple types of random number generation, and even alternate synchronization assumptions are all possible thanks to this flexibility. The needs of a network’s consensus algorithm will alter as it grows from hundreds to millions and ultimately billions of members. As a result, it’s critical to have enough flexibility to handle these changes and, as a result, future-proof the cryptocurrency’s core.

## ’The green blockchain’

The environmental effect of proof-of-work mining became a hot topic in 2021. Yahoo Finance,[^6] EuroNews[^7] and the Independent Newspaper[^8] were just some of those to dub Cardano the ‘green blockchain’. Cardano’s staking mechanism avoids Bitcoin mining’s huge energy consumption and hardware pollution. Bitcoin has been the subject of debate since Satoshi Nakamoto released the Bitcoin whitepaper[^9] in 2008. Cryptocurrency has been in the news a lot of times for all the wrong reasons. The most common objection is that Bitcoin mining, and other cryptos based on proofs of useless work[^10] protocols are harmful to the environment. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/cornel.png "Cornel Paper") 

Figure 3.1. Table from Cornel University Paper

According to a paper[^11] published by Cornell University, Bitcoin and Ethereum’s combined carbon footprint would rank 41st in the world. 

Algorithms for mining take a lot of power. This problem was exacerbated until recently by the fact that 70% of mining took place in China, where energy is generated using fossil fuels, notably coal. A crackdown by Chinese authorities has resulted in a crypto mining migration, which only shifted the issue to other nations. And the problem has ramifications in other areas. Concerns over energy use, for example, led to the banning of mining in Inner Mongolia.[^12] 

Bitcoin’s proof-of-work algorithm is it’s Achilles heel, yet essential to its operation. Mining rigs that are powerful and state-of-the-art create higher yields, but the quicker they are, the more energy they use. This raises the issue of long-term viability. According to a recent article on the Ethereum Foundation blog,[^13] ‘Ethereum’s power-hungry days are limited,’ and that the long-awaited switch to proof of stake would require 99.95% less energy.[^14] ‘The Merge’ finally took place in September 2022, however, the move to proof-of-stake has been anything but smooth with stakes locked up indefinitely and centralization concerns.[^15] It’s also just the first step on a convoluted roadmap to Eth 2.0. Since ‘the Merge’ was delayed for several years, it’s difficult to forecast when the rest of the roadmap will happen.

As Ethereum’s proof of work miners were effectively fired as a result of ‘the Merge’, an interesting discussion is ‘When Ethereum goes Proof of Stake, is Ergo likely to absorb most of the hash power?’[^16] 

But what distinguishes proof of stake from other blockchains in terms of environmental impact? Because miners must answer increasingly sophisticated mathematical problems to produce blocks, proof of work is resource intensive. They’re on a high-energy race across the world to solve meaningless, randomly generated problems. This vast amount of computing power might be put to better use like programming wind turbines or solar cells. This PoUW (Proof-of-useful-work) paper[^17] discusses alternatives to proof of work. This squandered digital effort has real-world ramifications.

The need for powerful hardware creates a further issue: e-waste. Miners must continually surpass their competitors, which necessitates the purchase of increasingly powerful mining equipment. ‘Old’ equipment, which is typically only fit for mining, soon becomes outdated. It is wasted, and Bitcoin’s e-waste is a growing problem. Because only 20% of electronic trash is recycled worldwide, the rigs’ plastics and dangerous elements, such as heavy metals, may wind up in landfills. By 2050, the United Nations predicts that the globe will create up to 120m tons of e-waste each year. This paper ‘Bitcoin’s growing e-waste problem’[^18] goes into greater detail.

So why is Cardano being dubbed the ‘green blockchain’? Cardano offers two distinct benefits when it comes to sustainability and environmentally friendly cryptocurrencies: considerably reduced energy use and staking. Network users run nodes in proof of stake, and the chain chooses a node to add the next block depending on the stake and other attributes of the node. The fundamental difference between these two algorithms (and hence their energy needs) is that block producers in proof of stake do not need to spend a lot of time and compute power solving random problems. Cardano’s energy consumption is projected to be 0.01% of Bitcoin’s.[^19] 

In a meaningless, energy-intensive arms race, proof-of-work cryptos need compute power to create blocks. A Cardano node, on the other hand, may operate on a low-power CPU like a Raspberry Pi. More than 40 million of these have been created, many of which are destined for schools in underdeveloped nations due to their low cost of $40-$70. This simplicity also cuts down on plastic and electronic waste.

Extreme weather and forest fires seem to increase each year, with the warnings from UN Climate reports becoming starker and starker. A report in April 2022[^20] insisted it was ‘now or never’. Society is aware of deforestation, ice shelf depletion, and global warming. Heatwaves are wreaking havoc on the ecosystem in many regions of the globe, and forest fires are ravaging numerous places. As a result, everything that contributes to the sustainability issue is scrutinized. This encompasses the expanding cryptocurrency market.

When it comes to solving environmental issues, there are no simple solutions. Cardano is a decentralized platform that can replace older and legacy systems’ inefficiencies. Cardano, and other proof-of-stake protocols, are considered to be contributing to the solution because of their sustainability credentials.

Although Cardano is a proof-of-stake blockchain and the focus of much of IOG’s work, they do research other protocols and have published extensively on Proof of work also. Their paper[^21] *Ofelimos: Combinatorial Optimization via Proof-of-Useful-Work: A Provably Secure Blockchain Protocol* was presented at Crypto 2022.

## Philosophy of POS

Decentralization is arguably Cardano’s most important and fundamental goal. The basis of every blockchain is its protocols and parameters. However, the community itself, how it perceives itself, acts, and establishes shared norms, is a major influence on the project’s success. Cardano has been meticulously architected to have ‘by design’ all of the qualities required for a successful blockchain system. Cardano is a social construct, and as such, adherence, interpretation, and social conventions all have a part in determining its robustness and long-term viability.

**Staking Principles**

Since the debut of the Bitcoin blockchain, consensus-based on a *resource* that is disseminated over a population of users – rather than identity-based participation – has been the hallmark of the blockchain ecosystem. Proof-of-stake systems are distinct in this space because they employ a *virtual resource* called stake that is recorded in the blockchain itself.

Pooling resources for participation is unavoidable; some amount of pooling is generally advantageous in terms of economics; therefore resource holders will find a means to make it happen. Given this inevitability, the challenge is then to avoid the emergence of a dictatorship, large entity, or oligarchy[^22] controlling too much stake. 

**Goal of Staking Rewards System**

Unlike previous blockchain systems, Cardano employs a reward sharing mechanism that (a) permits staking without unnecessary inconvenience and (b) incentivizes resource pooling in such a manner that system-wide decentralization develops spontaneously through resource holders’ rational engagement.

The mechanism’s two main goals are as follows:

- Involve all stakeholders - The more people who are involved in the system, the more secure the distributed ledger becomes. This also means that the system should have no participation barriers and should not cause friction by necessitating off-chain coordination amongst stakeholders to participate with the mechanism.

- Keep individual stakeholders’ power to a minimum - For certain stakeholders, pooling resources increases their influence. The power of pool operators on the system is proportional to the resources managed by their pool, not to their own. Without pooling, all resource holders have a leverage of one. The stronger the system’s leverage, the less secure it is (a 51%[^23] attack on the system is more likely).

A large pool size is not the sole cause of increased leverage; stakeholders may also gain leverage by forming several pools, either publicly or secretly (known as a Sybil attack).[^24] The greater the degree of decentralization of a blockchain system, the lesser its leverage.

**From Theory to Practice**

So, how does Cardano’s reward-sharing mechanism achieve the aforementioned goals? Staking with Cardano allows for two options: pledging[^25] and delegating. Stake pool operators use pledged stake; pledged stake is committed to a stake pool and is expected to remain there for the duration of the pool’s operation. Consider pledge to be a ‘commitment’ to the network. It’s a way to ‘lock up’ a specific amount of stake to help protect and secure the protocol. 

Delegating, on the other hand, is for individuals who don’t want to be hands-on. Instead, individuals are encouraged to evaluate the stake pool operators available and delegate their stake to one or more pools that, in their judgment, best serve their and the community’s interests. There is no reason to refrain from staking in Cardano since delegation does not involve the locking up of money. Liquid staking[^26] means you always have access to your ada. This is not a given with other proof-of-stake blockchains. 

For example, with Polkadot,[^27] your funds are ‘bonded’, which is a fancy word for ‘locked’. It takes a full 28 days to ‘unbond’ or ‘unlock’ your funds. That is generous compared to Ethereum, where stakers were not able to withdraw staked Ether prior to the *Shanghai* upgrade. Staking on Cardano is non-custodial, so there are no slashing[^28] penalties imposed. As a delegator, your staked funds are never at risk of being taken by the SPO, significantly adding to delegator participation.

Cardano’s incentive model is based on Nash equilibrium.[^29] The idea is that when stake pool operators and delegators are properly incentivized, then a Nash equilibrium will be reached based on their rational and honest behavior. The goal of the incentive mechanism is to achieve a high level of decentralization, security and participation.

Two parameters, *k* and *a0 (/a naught/)*, are crucial to the mechanism’s operation. Pool rewards are limited to 1/k of the amount available thanks to the k-parameter. Adding X amount of pledge to a pool boosts its rewards by up to a0*X, thanks to the *a0* option. This isn’t at the expense of other pools; any rewards that go unclaimed due to inadequate pledging will be restored to Cardano’s reserves and distributed in the future.

Creating a stake pool necessitates operators (aka stake pool operators, aka SPOs) declaring their profit margin[^30] and operating expenditures[^31] in addition to agreeing on an amount to pledge. The operating expenses are withheld first when the pool payouts are distributed at the conclusion of each epoch, ensuring that stake pools stay sustainable. Following that, the operator profit is determined, and all pool delegators are compensated in accordance with their investment.

This approach, when combined with the delegates’ evaluation of stake pools, offers the correct set of restrictions for the system to converge to a configuration of k equal-sized pools with the largest amount of pledge. 

Cardano’s blockchain architecture, like many others, has an innovative and well-researched mechanism. The rewards system has been mathematically shown to provide an equilibrium that matches its goals. But, in the end, arithmetic alone will not be enough; only humans will be able to make it happen. The future of Cardano lies in the hands of the community.

## Stake Pool Personas

A stake pool is a server node that aggregates and maintains the stakes of several stakeholders into a single entity. Stake pools oversee transaction processing and block production, and they monitor their interactions with the network via the Cardano node.

To manage a stake pool effectively, you’ll need a stake pool operator and one or more stake pool owners. There are conceptual differences between these two jobs:

- A stake pool operator is in charge of setting up and managing the stake pool, which means they own or rent a server, manage and monitor the node, and have access to the stake pool. Stake pool operators may sign blocks, register, re-register, and retire stake pools, as well as upload updated certificates, using their key

- A stake pool owner is someone who offers their stake to the pool to boost the pool’s reward earning capability and appeal. Sybil attacks are mitigated by the owner’s capacity to pledge stake.

The stake pool operator and owner are normally the same person, although a stake pool might have several owners who commit their share to establish a larger pool and maintain it competitively. Stake pool activities are still managed by a single stake pool operator in this case.

The stake pool operator must have the trust of all stake pool owners. All operator and owner rewards are placed into a single shared reward account linked to the pool’s reward address, and the protocol distributes them among the owner accounts. The reasoning for this is because if everyone could become a co-owner of a stake pool rather than delegating, the process would be rendered obsolete.

It’s advisable to have a contract to specify when and how the collected incentives in a shared account should be divided. They can, for example, agree to have the operator manage the shared account, or they can use a multisig[^32] account.

A bidirectional relationship and trust are required to run a pool properly. If this trust is betrayed, other parties may suffer losses in terms of accumulated or projected benefits, as well as the operator’s reputation.

The **controlled stake** is the entire amount of stake held by a stake pool. It combines the pool operator’s stake and any stakes that have been delegated to the pool by other ada holders. It may be expressed as a total quantity of ada (e.g., 2M ada) or as a percentage of the network’s total ada supply (e.g., 2%).

## Setting up and running a stake pool

Stake pools are an important aspect of the decentralized Cardano network, since they enable the procedures that assure the network’s long-term health and viability. Stake pool operators allow other users to participate in the system and earn rewards without having to host an active node all of the time. The scope of this book is to address the theoretical. 

More in-depth practical details are out of scope and covered in the Cardano Developer Portal.[^33]

## Cardano network

Federated nodes were solely responsible for block production and network connectivity in the Byron era. The Byron network was made up of federated core nodes, which were static nodes that created blocks and kept the Cardano network running. With the launch of Shelley, the network transitioned to a hybrid mode, with IOG-operated federated nodes (which configure connection between various stake pool operators) and SPO (stake pool operator)-operated nodes. The percentage of blocks produced by decentralized nodes steadily increased, while federated nodes progressively ceased operations, distributing network maintenance equitably across all stake pool operators. Using ongoing automated discovery and selection of peers, Shelley’s network migrated to complete decentralization.

Nodes linked to other nodes using a static configuration established in a topology file during the startup phase. It is critical to connect to dependable relay nodes to avoid a situation where relay nodes fall offline, rendering block-producing nodes unreachable. IOG provided SPOs with a list of all registered relays[^34] organized by geographical location for connecting reasons. SPOs should additionally produce a configuration that includes 20 other SPOs as peers. Many SPOs can employ more than 20 peers for connection reasons in practice. The list lets you choose peers both close and far away, ensuring inter-region connection.

The node’s network layer was altered to employ continuous automated discovery and peer selection as the network was shifted from federated to completely decentralized. Upgrades to the network stack were used to accomplish this. Initially, this allowed for enhanced automation of connecting SPO relays to one another, reducing the requirement for static setup. Dynamic peer-to-peer (P2P)[^35] networking came to the Cardano mainnet in March 2023. Nodes could now automatically communicate without the need for static configurations. More about this in the next chapter. 

More information regarding the Cardano network, node communication, and mini protocols that allow this capability may be found in the docs.[^36]

Core and Relay Node Connections

As a stake pool operator, you are concerned with two node types: core nodes and relay nodes. One or more relay nodes must accompany each core node. Core nodes are in charge of creating blocks, whilst relays are in charge of connecting with other relays in the network as well as broadcasting blocks. This distinction influences how they are set up and linked to the network.

For block generation, a core node is set up with several key pairs[^37] and an operational certificate. It only communicates with the relay nodes it has set up. Because a relay node does not need any keys, it is unable to create blocks. It communicates with its core node, relays, and external nodes. Each node should operate on its own server, with the firewall on the core node server set to only accept connections from its relays.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/relay.png "Core and Relay nodes") 

Figure 3.2: Core and Relay nodes

## How to choose a Stake Pools

Choosing a stake pool is not an exact science. There are many factors and delegators have different preferences, the process is entirely subjective. Some are attracted superficially to the pool with lowest fees, but on closer review, it is usually the least important consideration. If you are unsure about any of the parameters, or want to scrutinize a specific stake pool, you can dive deep with a favoured explorer tool such as the Cardano Foundation Explorer[^38] or peruse CardanoCube[^39] under ‘Tools and Explorers’

## Stake Pool Performance 

The creation of new blocks for the Cardano network is the responsibility of a stake pool designated as a slot leader.[^40] The slot will stay unfilled if the stake pool does not create a block, and the blockchain will not be extended. Although the Cardano blockchain may accept a few missing blocks, the bulk of expected blocks (at least 50% + 1) must be created within an epoch. Although missing blocks do not affect the blockchain’s overall extension, an unresponsive elected stake pool reduces the network’s overall speed.

The ratio of the number of blocks a stake pool generates in a particular epoch versus the number it was capable of producing is used to measure stake pool performance. For example, if a stake pool could create 100 blocks in an epoch (depending on its stake and likelihood of being elected), but only produced 50 blocks, its performance would be 50%. Poor stake pool performance reduces the quantity of rewards received by a pool and its members, making it less appealing to delegators. A stake pool should have adequate network connectivity, be run on a dependable system, and engage in block generation and verification to increase its performance.

The stronger the pool’s performance, the more appealing it will be to delegators, since higher rewards will be offered. Setting up and running a stake pool is not too challenging from a technical perspective. Marketing and attracting delegation to your pool is a competitive sport.

## Ranking Stake Pools

Stake pools are ranked in the Daedalus wallet and Cardano Explorer depending on the amount of rewards users will get if they opt to delegate to them. The ranking indicates the saturation[^41] level of the pool, making pool selection easier. From the standpoint of a delegator, once a pool reaches a specific saturation threshold, delegating to it is no longer profitable. The most desirable stake pools are shown first, and they are sorted from top to bottom.

The ranking system is intended to let users pick the best stake pool for a greater return on investment (ROI), so that dependable stake pool owners can keep the system running and maximize decentralization.

**Ranking parameters**

The cost and margin of a pool, as well as the pool’s performance and the amount of stake it has previously attracted, all factor towards its rating. These variables encourage the creation of dependable stake pools that are not yet saturated and provide low cost and margin.

The *Cardano Developer Portal includes guidelines for operating stake pools*[^42]  
## Types of Addresses in Cardano

The addresses are a blake2b-256 hash of the related verifying/public keys combined with some metadata stored on the Cardano blockchain.

Shelley introduced four different types of addresses:

- base addresses
- pointer addresses
- enterprise addresses
- reward account addresses

Aside from those addresses, Byron-era bootstrap[^43] and script addresses are still supported by Shelley. Only the new base and pointer addresses have stake rights. Addresses, such as a UTXO[^44] address, are made up of serialized data described in the ledger specification stored in the blocks of the blockchain.

There are two pieces to the serialized data (address):

- Metadata for interpreting.
- Payload: raw or encoded data

**Base Address**

The staking key that should manage the stake for that address is explicitly specified in a base address. The owner of the staking key can exercise the staking rights connected with funds kept at this address. Without first registering the staking key, base addresses may be used in transactions. Only by registering the stake key and delegating to a stake pool[^45] can the stake rights be exercised. After the stake key has been registered, stake rights can be exercised for base addresses used in transactions before or after the key registration.

**Pointer Address**

A pointer address indirectly specifies the staking key that should control the stake for the address. They are quite nuanced, and their practical use is open to question. They are not discussed in detail here because they are not intuitive to understand, but also because removing pointer addresses is a dependency for implementing a future version of Ouroboros. To dig into the technical reasoning, see the ongoing discussion on *CPS-0002 Pointer Address Removal*.[^46] CPS stands for ‘Cardano Problem Statement,’ a governance mechanism for proposing change. More on this later. 

**Enterprise Address**

Because enterprise addresses don’t come with stake rights, adopting them implies you’re opting out of the proof-of-stake protocol. Stake rights may not be exercised by exchanges or other entities that control substantial quantities of ada on behalf of other users. Exchanges may indicate that they observe this guideline by utilizing enterprise addresses. Enterprise addresses are automatically removed from the process that determines the slot leadership schedule since they are not connected with any staking key. Employing addresses with no stake rights reduces the overall amount of stake, which aids a prospective attack.

**Reward Account Address**

A reward address[^47] is a cryptographic hash of the address’s public staking key. To pay rewards for participating in the proof-of-stake protocol, reward account addresses are used (directly or via delegation).

They possess the following characteristics:

- Account-style accounting is employed rather than UTXO-style
- Transactions cannot be used to receive funds. Instead, when rewards are paid, their balance[^48] is just raised
- Registered staking keys and reward account addresses have a one-to-one relationship.

When funds are removed from the address, this key is used. Additionally, the stake connected with the funds in the address contributes to the stake of this key. The staking object for a reward address does not have to include any information, just as with enterprise addresses.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/address.png "Address structure")  

Figure 3.3: Cardano address structure, credit: aiken-lang.org/fundamentals/eutxo

The address is structured in 2, or sometimes 3 parts. An address always contains a header and payment credentials, but may also, optionally, contain delegation credentials. The header describes the address type and the network it is for, the delegation credentials part, while optional, is highly recommended. You have nothing to lose by not delegating your ada!

Credentials, whether payment or delegation, take one of two forms: a verification key hash, or a script hash. As the names suggest, payment credentials control how to spend from the address, while delegation credentials control how to publish certificates and how to withdraw staking rewards. A script allows a developer to code in some arbitrary validation logic.

Don’t worry if you don’t grasp every detail. It's just included for some context. We will elaborate more about scripts later. You can get even more forensic about addresses and their workings by reviewing the Cardano Improvement Proposal, CIP-19, Cardano Addresses.[^49]

## Pledging

Decentralization became a point of contention as Shelley approached on the Cardano mainnet. Proof-of-work cryptocurrencies like Bitcoin have grown increasingly centralized over time, regardless of their original founding aim. The days of Bitcoin fanatics mining blocks on AWS EC2 spot instances are long gone, and today’s mining networks are dominated by a tiny handful of specialized, professional mining companies.

This isn’t inherently a negative thing in and of itself, but it would go against Cardano’s idea of a decentralized, proof-of-stake system if it occurred. Cardano was built from the bottom up with decentralization in mind, especially in terms of stake delegation and reward systems. Pools larger than a certain size will not be competitive on the Cardano network, and delegation rewards for everyone will be ideal when there are numerous medium-sized pools. Diversity is beneficial to all ecosystems. Similarly, this method strikes the optimal mix between promoting grassroots participation from experienced community members and assisting individuals looking to start commercial stake pool firms.

**How Pledging Works**

A pool operator might pledge a personal investment in their pool upon registration to make it more appealing. The pledged sum may be modified epoch by epoch and will be refunded when the pool closes.

On the Cardano blockchain, anybody may run a pool. There is no minimum pledge. To make their pool more appealing, pool managers might pledge some or all of their stake to the pool. The more ada pledged, the more rewards will be given to the pool, which will attract more delegators.

It’s also worth noting that there’s also no maximum pledge, so a pool operator with a lot of ada to stake may maximize their own profits by filling up the pool with pledges and avoiding attracting any delegation. Of course, only a few operators will be able to do so; most will attempt to entice delegation with a mix of pledge, cheap costs, low profit-taking, and strong performance.

The appeal of a pool to delegators is determined by four interconnected factors:

- operating costs (lower the better)
- operator margin (lower the better)
- performance (higher the better)
- pledge (higher the better).

The pool operator might request a bigger operator margin while remaining desirable to delegators by offering a larger pledge.

**Pledging rewards**

Given two similar stake pools, the one with the higher pledge will receive more rewards and hence be more appealing to other delegators. The SPO (Stake pool operator) or other pool owners should work together to fulfill the pledge by delegating themselves. It’s also crucial to make sure there’s enough funds in the accounts that utilize the pool owner’s address(es) as stake reference. Failure to meet the pledge will result in no rewards for the pool being earned by any owner or delegators. This will almost always result in a loss of delegation and, in the worst-case scenario, pool collapse.

Unlike delegation, the SPO is in charge of all pledge rewards distribution. This may be done in any way that is mutually agreed upon and is not governed by the blockchain. 

**Why do we need pledging?**

Pledging on the Cardano blockchain is a technique for promoting a healthy economic environment. The pledge mechanism is also required to prevent Sybil attacks on the system. In such an attack, someone with very little personal stake establishes hundreds or thousands of pools with tiny margins and attempts to draw the bulk of stake to their pools. They can influence consensus and engage in double-spending attacks, create forks, censor blocks, and harm or even collapse the system if this succeeds. Such attacks are stopped by making pools with greater pledges more appealing, since an attacker must now divide their stake over many pools, making those pools less desirable and raising the inherent cost of executing a Sybil attack.

**How to measure the impact of Pledging**

Prior to the launch of Shelley on the Cardano mainnet, the parameter that affects pledging needed to be set. The parameter was created to be flexible and adaptable over time. The Shelley Haskell testnet was an excellent resource for fine-tuning this parameter and determining which values worked and which didn’t. IOG also created a calculator to assist pool operators estimate alternative pledge quantities and figure out how delegation could be affected.

Reasonable values are determined by a variety of variables, including: What percentage of a pool operator’s interest does he or she own? How much does it cost to run a node? How many people want to run a staking pool? During the Incentivized Testnet, a lot of data was acquired. 

IOG is committed to the scientific approach and that their architecture will result in a decentralized, stable, and secure blockchain— yet science and mathematics can only take you so far. Modeling assumptions must always be made, and no model will ever be as complex and colorful as what happens in practice.

On Reddit and on a ‘Cardano Effect’ episode, there was heated discussion on the matter. The Shelley Haskell testnets provided the ideal environment for continued debate. IOG evaluated, iterated and cooperated with stake pool managers to determine what is best for everyone. IOG enlisted the community’s support to put their findings into effect, much as they did with the Incentivized Testnet and Daedalus Flight user testing.

## Delegation

The practice of assigning individual stakeholders’ ada to collective stake pools is known as stake delegation. Delegation is used in block production to guarantee that the block is created in accordance with the proof-of-stake consensus. Stakeholders do not transfer stake ownership, voting rights, or other rights when they delegate.

To maintain confidence in the blockchain, large SPOs will often own a considerable amount of third-party stake, making them accountable for:

- block production
- transaction processing
- Cardano network maintenance
- ensuring the owner makes a pledge
- pool security (protecting its private keys.etc)
- updating the community about anything related to the pool.

The blockchain handles the distribution of block production rewards to delegators, so large operators aren’t concerned with it. SPOs are also not in charge of procuring delegated keys or acting on behalf of stakeholders in terms of delegation, voting, or other activities. Individual stakeholders must assume personal responsibility for their own security and make their own judgments on delegation, voting, and other matters.

Because Cardano is a proof-of-stake system, holding ada gives you the right, and duty, to participate in the protocol and build blocks in addition to allowing you to purchase products and services. Delegation of stake is a technique built into the Cardano proof-of-stake (PoS) protocol that enables it to grow even in the face of a widely dispersed group of stakeholders.

Anyone with ada may take part in the stake delegation process while keeping their spending power. Note that regardless of how you delegated your ada, you may spend it at any stage. In each epoch, the protocol allows stakeholders to engage in the slot leader election process. Stake delegation creates ‘stake pools,’ which function similarly to the Bitcoin protocol’s mining pools. When they are chosen as slot leaders, stake pool operators must be online in order to create blocks.

**Stake delegation requirements**

Delegating stake involves uploading of two certificates to the chain: a staking address registration and a delegation certificate. Because posting certificates necessitates funds, a user who is just getting started with their wallet needs a bootstrapping method. This approach is based on the ability of base addresses using staking keys before publishing the key’s registration certificate. The stake address can be based on a single key or a script like multi-sig.

**Delegation Scheme**

With the notion of delegation, any stakeholder may authorize a stake pool to create blocks for the Cardano network, and the protocol will subsequently distribute the rewards to all participants, including the stake pool operators’ fees. A stakeholder is assigned to a specific pool ID, which is a hash of the operator’s verification key.

The stakeholder may restrict the proxy signing key’s valid message space to strings ending with a slot number in a certain range of values to limit the delegate’s block generating capability to a specific range of epochs and slots. Due to the verifiability and abuse prevention qualities of proxy signature schemes, this basic scheme is reliable. This guarantees that every stakeholder can verify that a proxy signing key was granted to a particular delegate by that stakeholder and that the delegate may only use these keys to sign messages inside the key’s valid message space.

A single transaction with a delegation certificate is required to post funds belonging to one staking key of a user’s wallet. Only the standard transaction fees will apply. A stakeholder must pay a deposit to register a stake address, not for the stake delegation itself. After registering a stake address, the stakeholder will simply have to pay fees for their chosen delegation. During the rewards process, the stakeholders’ stake will be considered part of the pool’s stake. 

## Pledging and rewards

Pledging is a critical method for fostering the development of a healthy ecosystem on the Cardano blockchain. You may pledge part or all of your ada to a stake pool when you register it to make it more appealing to others who wish to delegate. Although pledging is not mandatory when creating a stake pool, it may make it more desirable to delegators since the bigger the quantity of ada pledged, the higher the rewards given out. The a0 protocol parameter specifies how the pledge affects the pool reward. There is no optimal pledge amount, it depends on the pool and personal preference. The more you pledge the higher the rewards.

**Rewards Distribution** 

Rewards are issued to all stakeholders who have delegated to a stake pool, either their own or another pool, at the end of each epoch. The protocol generates these rewards and does not rely on the stake pool operators to administer them. There are two types of rewards:

- transaction fees: compiled from the collection of transactions contained in a block minted (generated) in that epoch

- Monetary expansion entails determining the difference between the total and maximal supply of ada. All ada now in circulation, as well as ada held in the treasury, make up the total supply. The maximal supply refers to the most ada that can ever exist (45 billion ada). The reserve is the difference between these two amounts. A predetermined proportion of the remaining reserve is withdrawn during each epoch and used for epoch rewards and treasury, with the amount transferred to the treasury being a set percentage of the amount taken from the reserve.

IOG’s chief scientist Professor Aggelos Kiayias discusses more in this *Rewards sharing and pledge on Cardano* video.

Remember that the pledge is expressed (together with the cost and margin amounts) during pool registration and must be fulfilled by the pool owners who are delegating to the pool: Pool rewards for that epoch will be 0 if they collectively delegate less than the specified pledge. If the pool’s operator margin is set to less than 100%, the pool will be public.

## Pledging and Delegation Options

On the Cardano network, ada reflects a user’s stake in the protocol, with the amount of the stake proportional to the number of ada possessed. Cardano users may receive passive rewards for verifying blocks if they have a stake in the cryptocurrency. The quantity of ada they pledge or delegate to a stake pool determines the amount of rewards they may receive.

Ada holders have 3 options when it comes to delegating their stake:

- They are in charge of their own stake pool.
- Rely on third party to manage a private stake pool on their behalf, such as Kraken, one of the oldest Crypto exchanges.
- Delegate to other stake pools

See the create transaction instructions for advice on how to set up a stake pool, pledge, delegate and earn ada rewards.

Stake pools must maintain high availability, which means they must be accessible to verify and produce new blocks at all times. The quantity of ada committed or delegated, as well as the number of blocks a stake pool may build in a particular epoch, determine the rewards a stake pool can get. Based on the aforementioned criteria, Ouroboros, the backbone of the Cardano protocol, elects the slot leader that grants permission to process transactions and mint new blocks.

Note: Before deploying to the mainnet, all stake pool functionality should be thoroughly tested on the testnet.

**Pledging**

When a stake pool is launched, the stake pool operator’s pledge is the amount of ada that they ‘delegate’ to their own pool. The operator’s commitment to maintain their pool and promote network activity can be seen in the pledge. It is not necessary to make a pledge, however it is suggested that you do so before starting the stake pool. The greater the pledge, the more rewards for the pool which is contingent on the pool’s uptime and performance.

**Delegation**

Delegating to any stake pool accessible on the network might yield rewards for ada holders who do not have technical knowhow in operating a stake pool. Multi-pool delegation has been a sought after feature for some time. It finally came to fruition in 2023 with Lace wallet offering the feature. *Strica* (makers of Typhon wallet) questioned the trade offs involved in how this feature was implemented and if it could be offered more smoothly. Meanwhile, *Atrium Labs* have been blogging about a new innovation called *staking baskets* which will allow users to stake to multiple pools via  smart contract that will be open-sourced. 

Note: holders of ada and SPOs (stake pool operators) who pledge, or delegate will always have access to their ada. The rewards drop proportionately when the delegated ada is spent or withdrawn from the pool.

**Rewards**

For engaging in staking (either pledging or delegating), delegators earn rewards, which are immediately divided among the participants according to the rewards plan. Cardano’s reward system is decentralized, meaning there is no one governing entity. Rewards are calculated by the Ouroboros protocol and generally are about 3-4% assuming you have delegated to an unsaturated stake pool. If the amount of ada delegated to a given stake pool is over a set amount, the pool is deemed to be oversaturated. The delegating tab in most light wallets will display useful stats and details on each of the stake pool delegation candidates. 

Rewards are distributed each epoch to stake pools for validating blocks. The staking and rewards should not be confused with earning interest. Interest is a fixed sum promised to a recipient, whereas there is a random element in distributing rewards, with the onus on the ada holder to delegate to a pool that is not saturated. Pooltool.io has a friendly dashboard where you can review all kinds of ‘live’ staking stats.

**Open source rewards calculation**

To dig deeper still, you can review the Cardano ledger specifications which outline formulas used to calculate staking rewards. As part of the Cardano Foundation’s remit to drive operational resilience of the network, they open sourced a node-independent reward calculation. The project is quite technical and beyond the scope of this book so best to review the CF blog post for more details. At a high level, the project aims to offer a means of performing and validating the rewards calculation that is independent of a single implementation. In doing so, the CF will share comprehensive documentation related to Cardano’s treasury, reserves, and pool rewards.

## Types of Keys in Cardano

Asymmetric cryptography key pairs known as keys are used for:

- Securing payments and staking certificates by signing and verifying them
- Identifying and defining addresses.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/keys.png "Cardano Keys")  

Figure 3.4. The link between keys, addresses, and certificates:

There are two main types of keys in Cardano:

- Node keys
- Address keys

**Node Keys**

The following keys make up the node keys, which constitute the blockchain’s security.

- Operator/operational key
- KES key pair
- VRF keys

**Operator/operational key**

These are offline key pairs for operators that include a certificate counter for new certificates. The operator is responsible for managing both the hot (online) and cold (offline) keys for the pool. Cold keys must be kept secure and should not be stored on a device that has internet access. Cold key backups should be kept in several locations.

**KES key pair**

A Key Evolving Signature (KES) key pair, which authenticates who you are, is required to establish an operational certificate for a block-producing node.

A KES key can only evolve for a set amount of time (a certain number of epochs) before becoming worthless. This is important because, even if an attacker compromises the key and has access to the signing key, he can only use it to sign blocks going forward, not blocks from previous epochs, preventing the attacker from rewriting history.

The node operator must produce a new KES key pair, issue a new operational node certificate with the new key pair, and restart the node with the new certificate when the specified number of epochs have elapsed.

**VRF keys**

Ouroboros Praos (Ouroboros versions are explained later, in Chapter 4) provided an additional degree of protection by using Verifiable Random Function (VRF) keys in block production. VRF makes the consensus protocol difficult to attack because it’s impossible to predict the next producing nodes.

Because the slot leader schedule is known in other proof-of-stake blockchain protocols (such as Ouroboros Classic or BFT), it’s known who has the authority to create the block in each slot. In this instance, you have to establish that you are who you claim you are, and anybody can verify this by looking at the public slot leader schedule. This process was subsequently improved in the Feb 2022 release, with a new CLI tool for SPOs to check their own slot leadership schedule.

Ouroboros Praos’ slot leader schedule, on the other hand, is kept private, which means that no one knows who the slot leader in advance will be, but once they are, they can verify to everyone else that they are using the VRF key.

The VRF key is a signature verification key that is recorded in the operating certificate. It establishes a node’s permission to produce a block in a certain slot. 

**Address keys**

The purposes of address keys are derived from the keys for identifying ada on the blockchain, which include the following keys:

Payment key: a single address key pair that is often used to create UTXO addresses
Staking key: a key pair consisting of a stake and a reward address that is typically used to generate account and reward addresses.

**Signatures**

If a cryptocurrency uses a single signature scheme, it must accept the risk that the scheme may be broken in the future, and that at least one entity will be unable to utilize the cryptocurrency owing to legal or industry constraints. However, a cryptocurrency cannot support all signature schemes since each client would have to comprehend and verify each scheme.

For Cardano, IOG chose to start with elliptic curve encryption, specifically the Ed25519 curve.

Cardano enabled additional signature systems post ‘Vasil’ hard fork in the subsequent ‘Valentine’ update in February 2023, and the Chang hard fork due in 2024. Quantum computer-resistant signatures will be included into the system. Cardano was built with specific features that enable a soft fork and the addition of new signature schemes. They will be included when required and as part of the roadmap’s major releases. 

**March 19, 2020, in response to the US Senate bill and prose to outlaw encryption.** CH:


>I think that’s equivalent to the ability to outlaw gravity or to change Pi to 3. I mean people can certainly say stuff and try to do things, but you cannot enforce something as crazy as outlawing encryption …it’s like how would the internet even work? SSL (secure sockets layer) is now illegal? You have to have certificate authorities …put a man-in-the-middle attack for every single website? Does the US government enforce that? It’s old people who have no clue how the internet works, or technology works, playing and fiddling with things …and they should be in diapers instead of voting.

## Cardano tracking tools   

Because Cardano is a public blockchain ledger, many tools may be used to conveniently follow all recent transactions, block information, and epoch data.

**Exploring transactions and blocks**

Cardano Explorer is a user-friendly application that pulls information from the main database and displays it in an easy-to-use online interface.

By selecting a single block, you may discover more about it, including its ID, size, epoch, and block data, as well as the number of transactions and confirmations contained. You may also use the search area to look for certain epochs, transactions, or blocks by pasting their IDs.

The Cardano Foundation talks regularly with regulators and auditors to clarify the nuances of proof of stake (PoS). It is crucial they understand that not all PoS blockchains are the same. The Cardano Explorer has become a useful tool in explaining how Cardano functions. There are sections to explain the staking lifecycle and a smart contract visualization user interface (UI). More features are planned, it’s best to check the release notes on GitHub for the latest. 

**Explorer options**

There’s a whole gamut of tools such as cardanoscan.io, cexplorer.io and many more listed under IOG’s Essential Cardano, the Cardano Developer Portal, as well as third party sites like CardanoCube (cardanocube.io) and BuiltOnCardano (builtoncardano.com).

Multi-asset generation and administration are supported by Cardano. You may use tools such as Cardano Assets (cardanoassets.com) and Cardanoscan (cardanoscan.io/tokens) to view a list of assets and tokens. Everyone has their favorite, mine are taptools.io and eutxo.org You can use these tools like Adapools (adapools.org) and Pool.pm (pool.pm/search) to get a list of all active stake pools, their tickers, pool names, and IDs. 

## Getting hands on   
Static text in a book is perhaps not the best medium to explain how to get hands-on with wallets and staking. There are numerous YouTube guides on how to use any of the 20+ light wallets available. We talked about the theory and design of Cardano staking in this chapter. In practice, it is a seamless ‘point and click’ experience in most wallets UIs today. The CF provides a free online course which is geared towards those taking the *Cardano Blockchain Certified Associate* exam. You can review more about the course overview here where module 4 guides you the practical steps of buying ada, staking and other beginner steps.

[^1]: In a **synchronous system**, operations are coordinated by one, or more, centralized clock signals. An asynchronous digital system, in contrast, has no global clock. Asynchronous systems do not depend on strict arrival times of signals or messages for reliable operation. Coordination is achieved via events such as: packet arrival, changes (transitions) of signals, handshake protocols, and other methods.
[^2]: Berry Pool, github.com/alessandrokonrad/Pi-Pool
[^3]: **Raspberry Pi**: computer on a credit-card-sized board. Idea developed by Eben Upton and others from Cambridge University’s Computer Lab and launched by their Raspberry Pi Foundation. Taking inspiration from the 1980s BBC Computer Literacy Project, the single-board computer running Linux with open-source software was launched in 2012 costing £22 to encourage computing in schools and the developing world.
[^4]: Cardano on the Rocks: energy efficient proof-of-stake stake pools, youtube.com/watch?v=kXR1UXkM46s
[^5]: A **light client** is a lightweight computer that has been optimized for establishing a remote connection with a server-based computing environment. The server does most of the work, which can include launching software programs, performing calculations, and storing data. This contrasts with a fat client or a conventional personal computer; the former is also intended for working in a client–server model but has significant local processing power, while the latter aims to perform its function mostly locally.
[^6]: Take the green blockchain to the next level with Cardano, finance.yahoo.com/news/green-blockchain-next-level-cardano-192654597.html
[^7]: Could Cardano’s ‘green’ cryptocurrency ADA take over Bitcoin and Ethereum?, euronews.com/next/2021/08/23/could-cardano-s-green-cryptocurrency-ada-take-over-bitcoin-and-etherium
[^8]: What is Cardano? The ‘green’ crypto that defied Musk’s bitcoin crash – and hopes to surpass Facebook and Netflix, independent.co.uk/space/cardano-crypto-bitcoin-elon-musk-b1849021.html
[^9]: Satoshi Nakamoto, ‘Bitcoin: A Peer-to-Peer Electronic Cash System’, bitcoin.org/bitcoin.pdf
[^10]: Dotan and Tochner, ‘Proofs of Useless Work: Positive and Negative Results for Wasteless Mining Systems’, arxiv.org/pdf/2007.01046.pdf
[^11]: An Analysis of Energy Consumption and Carbon Footprints of Cryptocurrencies and Possible Solutions, arxiv.org/pdf/2203.03717.pdf
[^12]: Major bitcoin mining region in China sets tough penalties for cryptocurrency activities, cnbc.com/2021/05/26/major-china-bitcoin-mining-hub-lays-out-harsher-crackdown-measures.html
[^13]: Ethereum’s energy usage will soon decrease by ~99.95%, blog.ethereum.org/2021/05/18/country-power-no-more/
[^14]: This breakthrough could make Ethereum more environmentally friendly than Bitcoin, fortune.com/2021/05/24/ethereum-bitcoin-buterin-carbon-footprint-proof-of-stake/
[^15]: What Does the Ethereum Merge Mean for Crypto?, builtin.com/blockchain/ethereum-merge
[^16]: Roundtable with Charles Hoskinson and Alex Chepurnoy | Ergo Pulse, youtu.be/k9a3SYV6FJA?t=3182
[^17]: A novel proof of useful work for a blockchain storing transportation transactions, sciencedirect.com/science/article/pii/S0306457321002302
[^18]: Bitcoin’s growing e-waste problem, sciencedirect.com/science/article/abs/pii/S0921344921005103
[^19]: What is Cardano? The ‘green’ crypto that defied Musk’s bitcoin crash – and hopes to surpass Facebook and Netflix, independent.co.uk/life-style/gadgets-and-tech/cardano-crypto-bitcoin-elon-musk-b1849021.html
[^20]: UN climate report: It’s ‘now or never’ to limit global warming to 1.5 degrees, news.un.org/en/story/2022/04/1115452
[^21]: Fitzi, Kiayias, Panagiotakos, Russell (2022), 'Ofelimos: Combinatorial Optimization via Proof-of-Useful-Work: A Provably Secure Blockchain Protocol', iohk.io/en/research/library/papers/ofelimos-combinatorial-optimization-via-proof-of-useful-work-a-provably-secure-blockchain-protocol/
[^22]: **Oligarchy**, meaning ‘few’, and ‘to rule or to command’, is a form of power structure in which power rests with a small number of people.
[^23]: A **51% attack** is a hostile takeover of a Cryptocurrency validated via proof-of-work Algorithms through the acquisition of the majority of the network's hashing power.
[^24]: In a **Sybil attack**, the attacker subverts the reputation system of a peer-to-peer network by creating a large number of pseudonymous identities and uses them to gain a disproportionately large influence. It is named after the subject of the book Sybil, a case study of a woman diagnosed with dissociative identity disorder.
[^25]: **Pledging**: when a stake pool operator assigns their own ada stake to support their stake pool. This provides protection against Sybil attacks by preventing pool owners from creating a large number of pools without themselves owning a lot of stake.
[^26]: **Liquid staking** allows users to stake their funds while actively participating in securing proof-of-stake blockchains. You can still access your funds, or use it to participate in other DeFi protocols. Your fund, ada, is never locked or ‘bonded’.
[^27]: Polkadot staking, wiki.polkadot.network/docs/learn-staking
[^28]:  **Slashing** is a mechanism used by PoS protocols to discourage harmful behaviors and make validators more responsible. They help keep the network secure since, without slashing penalties, a validator can use the same node to validate blocks on multiple chains or do so on the wrong chain.
[^29]:  **Nash equilibrium** is used in game theory for modeling and defining the solution in a game where players do not cooperate together.
[^30]: **Profit margin**: The stake pool operator takes a portion of total ada rewards before dividing the remainder of the rewards with all of the pool’s delegators. If the operator’s profit margin is low, they’re taking less risks, which means delegators should anticipate reaping more of the rewards for their delegated stake. A private pool is one with a profit margin of 100%, indicating that the operator receives all of the rewards and the delegators get none.
[^31]: **cost per epoch**: The stake pool operator deducts a predetermined charge from the pool payouts every epoch to cover the expenses of maintaining a stake pool. Before the operator collects their profit margin, the cost per epoch is removed from the total ada that is awarded to a pool. Whatever is left is divided evenly among the delegators.
[^32]: **Multisignature** (multi-signature) is a digital signature scheme which allows a group of users to sign a single document. Usually, a multisignature algorithm produces a joint signature that is more compact than a collection of distinct signatures from all users. Multisignature can be considered as generalization of both group and ring signatures providing additional security for cryptocurrency transactions.
[^33]: Operate a stake pool, developers.cardano.org/docs/operate-a-stake-pool/
[^34]: List of registered relays, explorer.cardano-mainnet.iohk.io/relays/topology.json
[^35]: **Peer-to-peer (P2P)**: distributed application architecture that partitions tasks or workloads between peers. Peers are equally privileged, equipotent participants in the application. They are said to form a peer-to-peer network of nodes. In Cardano this involves sending transactions (or files) directly between nodes in a decentralized system without relying on a centralized authority.
[^36]: Understanding the Relay and Block Producer topology, developers.cardano.org/docs/operate-a-stake-pool/stake-pool-networking
[^37]: **Key pair**: Public-key cryptography, or asymmetric cryptography, is a cryptographic system that uses pairs of keys: public keys which may be disseminated widely, and private keys which are known only to the owner. The generation of such keys depends on cryptographic algorithms based on mathematical problems to produce one-way functions. Effective security only requires keeping the private key private; the public key can be openly distributed without compromising security. Within the blockchain, these keys are used to process and authorize transactions.
[^38]: Cardano Foundation Explorer, beta.explorer.cardano.org/en/
[^39]: CardanoCube, cardanocube.io/cardano-ecosystem-interactive-map
[^40]: Slot leader, developers.cardano.org/docs/stake-pool-course/introduction-to-cardano/
[^41]: **Saturation**: a word that refers to a stake pool that has more stake delegated to it than is optimal for the network. The saturation level is expressed as a percentage. When a stake pool achieves 100% saturation, the rewards start to shrink. The saturation mechanism was created to avoid centralization by encouraging delegators to delegate to multiple stake pools and operators to build up alternative pools in order to keep receiving maximum rewards. Saturation aims to safeguard both the interests of ada holders delegating their stake and the interests of stake pool operators.
[^42]:  Guidelines for large SPOs, developers.cardano.org/docs/get-started/
[^43]: In general, **bootstrapping** usually refers to a self-starting process that is supposed to proceed without external input. In computer technology the term (usually shortened to booting) usually refers to the process of loading the basic software into the memory of a computer after power-on or general reset, especially the operating system which will then take care of loading other software as needed.
[^44]:  An **unspent transaction output (UTXO)** is the technical term for the amount of digital currency that remains after a cryptocurrency transaction.
[^45]: Stake Pools, docs.cardano.org/core-concepts/stake-pools
[^46]: CPS-0002 Pointer Address Removal, github.com/cardano-foundation/CIPs/pull/374
[^47]: **Rewards Wallet**: a wallet that contains ada and may be used to delegate stakes. A stake may only be delegated to a single stake pool from a single Rewards wallet. You’ll need to construct numerous Rewards wallets and divide ada across them if you want to delegate to more than one stake pool. Split pool delegation has been promised by IOG for some time but has been postponed, to allow focusing resources on other roadmap priorities.
[^48]: **Balance wallet**: your original testnet ada balance, copied from the mainnet through the balance snapshot, is stored in this wallet. This wallet’s stake is not transferable, although it may be moved to and delegated from a Rewards wallet.
[^49]: Cardano addresses, cips.cardano.org/cip/CIP-0019
[^50]: Can we use AWS spot instances for guaranteed mining profits?, stackoverflow.com/questions/51665962/can-we-use-aws-spot-instances-for-guaranteed-mining-profits
[^51]: Lars Brünjes, ‘Preventing sybil attacks’, iohk.io/en/blog/posts/2018/10/29/preventing-sybil-attacks/
[^52]: **Double-spending** is a potential flaw in a digital cash scheme in which the same single digital token can be spent more than once. Unlike physical cash, a digital token consists of a digital file that can be duplicated or falsified. As with counterfeit money, such double-spending leads to inflation by creating a new amount of copied currency that did not previously exist. This devalues the currency relative to other monetary units or goods and diminishes user trust as well as the circulation and retention of the currency. Fundamental cryptographic techniques to prevent double-spending, while preserving anonymity in a transaction, are blind signatures and, particularly in offline systems, secret splitting.
[^53]: Kevin Hammond, 'From Byron to Shelley: Part one, the testnets', iohk.io/en/blog/posts/2020/04/29/from-byron-to-shelley-part-one-the-testnets/
[^54]: Cardano Calculator, cardano.org/calculator/?calculator=operator
[^55]: Cardano Mainnet: Pledge Influence Factor Analysis, 
reddit.com/r/cardano/comments/gfed1l/cardano_mainnet_pledge_influence_factor_analysis/
[^56]: Pledge Influence Factors, Effects on Operators and Stakers, with Umed Saidov | TCE 88, youtube.com/watch?v=ubWIytFZYGE
[^57]: **Daedalus Flight** is a ‘pre-release’ version of the Daedalus wallet.
[^58]: Anthony Quinn, ‘We need you for a Daedalus testing program!’, iohk.io/en/blog/posts/2020/04/01/we-need-you-for-the-daedalus-flight-testing-program/
[^59]: Cardano founder shares proxy keys idea to implement, coinregwatch.com/cardano-founder-shares-proxy-keys-idea-to-implement/
[^60]: **Proxy signature** is a special type of digital signature which allows one user (original signer) to delegate his/her signing right to another signer (proxy signer). The latter can then issue signatures on behalf of the former.
[^61]: Rewards sharing and pledge on Cardano, youtube.com/watch?v=EAzyN3H8MOA
[^62]: Earn 4-6% Staking Cardano (ADA), Available on Kraken Now!, blog.kraken.com/post/8891/earn-4-6-staking-cardano-ada-available-on-kraken-now/
[^63]: Create a simple transaction, developers.cardano.org/docs/stake-pool-course/handbook/create-simple-transaction/
[^64]: Lace multi-pool delegation feature, lace.io/blog/stake-your-ada-across-multiple-pools-with-lace-s-new-multi-delegation-feature-beta
[^65]: Thoughts on Multi-Delegation and Staking Portfolios, medium.com/@StricaHQ/thoughts-on-multi-delegation-and-staking-portfolios-ead8a8e2436e
[^66]: Atrium Labs staking basket, medium.com/atrium-lab/staking-baskets-687030683574
[^67]: Cardano ledger specs, github.com/IntersectMBO/cardano-ledger
[^68]: Releasing an open source rewards calculation, cardanofoundation.org/en/news/releasing-an-open-source-rewards-calculation/
[^69]: Public-key cryptography, or asymmetric cryptography, is a cryptographic system that uses pairs of keys: public keys which may be disseminated widely, and private keys which are known only to the owner. Effective security only requires keeping the private key private; the public key can be openly distributed without compromising security.
[^70]: Why use key evolving signatures, forum.cardano.org/t/why-use-key-evolving-signatures/11133/4
[^71]: Tim Harrison, ‘From node enhancement to block leadership… Cardano’s February release’, iohk.io/en/blog/posts/2022/02/28/from-node-enhancement-to-block-leadership-cardano-s-february-release
[^72]: In public-key cryptography, **Edwards-curve Digital Signature Algorithm (EdDSA)** is a digital signature scheme using a variant of Schnorr signature based on Twisted Edwards curves. It is designed to be faster than existing digital signature schemes without sacrificing security.
[^73]: Surprise AMA 03/19/2020, youtu.be/9rClM2pLNmo?t=2406
[^74]: Transport Layer Security (TLS) and its predecessor, **Secure Sockets Layer (SSL)**, are cryptographic protocols that provide communications security over a computer network.
[^75]: Cardano Foundation Explorer release notes, github.com/cardano-foundation/cf-explorer/releases/
[^76]: Essential Cardano, github.com/input-output-hk/essential-cardano/blob/main/essential-cardano-list.md
[^77]: Cardano developer portal, developers.cardano.org/showcase
[^78]: Cardano Blockchain Certified Associate, academy.cardanofoundation.org/overview



**_To be uploaded soon..._**
