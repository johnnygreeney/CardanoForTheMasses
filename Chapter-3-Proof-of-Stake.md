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
