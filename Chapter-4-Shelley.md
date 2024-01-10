# Chapter 4: Shelley (Consensus)

*‘If winter comes, can spring be far behind?’* ― Percy Bysshe Shelley

## The Scalability Challenge

Distributed systems are made up of a group of servers[^1] (nodes) that have agreed to execute a protocol, or a collection of protocols, to achieve a shared purpose. This objective might be as simple as distributing a file using the BitTorrent protocol,[^2] or decentralized storage.[^3] 

As more nodes join the network, the most efficient protocols acquire resources. If several peers are simultaneously downloading a movie file provided by BitTorrent, for example, it may be downloaded substantially quicker on average. Because peers both contribute and use up resources, the speed increases. When someone says a distributed system scales, they’re usually referring to this feature.

The problem with most existing blockchain protocols is that they were not built to be scalable in the first place. Blockchains, for example, are often a linked list of blocks that can only be added to. A blockchain protocol’s security and availability are dependent on numerous nodes having a complete copy of the blockchain data. As a result, N nodes must copy a single bit of data. Additional nodes place a burden on resources required. 

This is true for both transaction processing and gossip protocol[^4] across the system. Increasing the number of nodes in the consensus system does not increase transaction processing power. It simply indicates that more resources are required to do the same task. More network relaying means that more nodes must send the same messages to keep the whole network in sync with the most recent block.

Cryptocurrencies cannot grow to a worldwide network, comparable to older financial systems, due to their structure. Legacy infrastructure, on the other hand, is scalable and can handle orders of magnitude greater processing and storage power. Bitcoin is a relatively tiny network in comparison to its payment counterparts such as Visa, Mastercard, PayPal, etc and it is currently struggling to handle its present load.

The Ouroboros consensus protocol boosts scalability for Cardano. It allows for the decentralized election of a quorum of consensus nodes, which may then execute more conventional protocols to meet the demands of huge infrastructure providers like AWS, Google and Facebook.

For example, electing a quorum for an epoch implies there is a trustworthy group of nodes to keep the ledger up to date for a specified length of time. It is simple to elect many quorums at the same time and divide transactions among them.

## What is a Consensus Protocol?

A consensus protocol is a collection of rules and parameters that regulate the behavior of distributed ledgers: a set of rules that each network member must follow. There is no one central authority in charge of public blockchains. Instead, a consensus mechanism is employed to enable dispersed network users to agree on the network’s history as recorded on the blockchain - to achieve agreement on what has occurred and proceed from a single source of truth.

A single record is provided by that one source of truth. This is why blockchains are frequently referred to as ‘trustless,’ since trust is built into the protocol rather than needing users to trust one another. Unknown actors may communicate and trade with one another without requiring the mediation of a third party or the sharing of personal data.

Consensus is the method through which everyone participating in the blockchain’s operation comes to an agreement. There must be unanimity on which blocks to generate, which chain to use, and how to establish the network’s single state. Individual nodes examine the current state of the ledger and form a consensus using the consensus protocol Ouroboros. It has three key responsibilities: doing a leader check and deciding whether a block should be created, handling chain selection, and verifying blocks that have been produced.

Blockchains achieve consensus by enabling users to group transactions submitted to the system into blocks and add them to their own chain (sequence of blocks). The objective of the various consensus protocols is to determine who is permitted to generate a block? When? …and what to do in the event of a disagreement? For example, what if two participants add different blocks at the same time? There are many different types of consensus protocols,[^5] the main two being proof of work and proof of stake. Ouroboros is a consensus mechanism based on proof of stake that has been shown to have the same level of security as proof of work. 

## Ouroboros

Ouroboros is a mythological creature represented as a snake, or dragon, devouring its own tail in a closed circle. The name ‘Ouroboros’ comes from Ancient Greek and literally means ‘tail eater’ or ‘tail devourer.’

Ouroboros is a symbol for infinity of time flowing back into itself in an endless circle, as if trapped in an unending loop. The first appearance of the Ouroboros was in Egypt in the 13th century BC. Alchemists later used Ouroboros in their mystical symbolism. Ouroboros has been understood and employed in a number of ways by many civilizations throughout history. One of the most prevalent interpretations of the symbol is that it signifies the Universe’s interconnection and infinity.

Charles Hoskinson named Cardano’s proof-of-stake consensus Ouroboros in 2017. In this sense, Ouroboros reflects the blockchain’s potential for endless growth and scalability. The core theme of Ouroboros is the provision of expanded possibilities for the planet, as well as its preservation through drastically decreased energy usage.

Ouroboros was the first blockchain consensus system to be created via peer-reviewed research as a more energy efficient and sustainable alternative to proof of work, which is the foundation of previous cryptocurrencies such as Bitcoin and, until recently, Ethereum. Ouroboros and its various iterations give a new foundation for solving some of the world’s toughest issues safely and at scale.

Ouroboros ensures the security and sustainability of any blockchain that uses it by combining unique technology and mathematically validated methods (including behavioral psychology and economic philosophy ideas). Ouroboros has demonstrated to be secure and capable of facilitating the spread of global, permissionless networks with little energy consumption. Cardano is the first network of its kind. Ouroboros enables users - in this example, stake pools - to establish new blocks based on the amount of stake they own in the network, and thus enable the creation of a distributed, permissionless network. 

## The different implementations of Ouroboros 

**May 25, 2020. re: Ouroboros.** CH:

> So if I had to succinctly say ..’well what is Ouroboros?’... I’d say it’s a first principles-based, new way of doing consensus that keeps the stuff we’ve come to know and love from Bitcoin, that’s very useful and great, but then does it in a much more sustainable energy-friendly way, that also allows you to layer on many more utilities than just mining to the system. It does so in a way that attracts lots of competition, lots of decentralization and lots of businesses. Mining tends to centralize to a small group of actors because of economy of scale

**Ouroboros Classic**

Ouroboros Classic was the first implementation released in 2017. It established the protocol as an energy-efficient alternative to proof of work, provided a mathematical framework for analyzing proof of stake, and presented a unique incentive mechanism for proof-of-stake users.

What set Ouroboros apart from previous blockchains and other proof-of-stake protocols was its capacity to provide unbiased randomness in the protocol’s leader selection method, as well as the security guarantees that came with that. Randomness prevents patterns from forming and is an important aspect of the protocol’s security. When a behavior can be expected, it may be manipulated — and although Ouroboros assures transparency, it prevents coercion. Ouroboros is notable for being the first blockchain technology to undergo such thorough security testing.

The research paper on Ouroboros has in depth explanations of its functionality. The blockchain is divided into slots and epochs by Ouroboros. Each slot in Cardano lasts 1 second, and each epoch (which is a collection of slots) comprises five days’ worth of slots.

The awareness that attacks are unavoidable lies at the heart of Ouroboros’ design. As a result, the protocol includes tolerance to prevent attackers from spreading other copies of the blockchain, and it assumes that an opponent may transmit arbitrary messages to any member at any moment. In reality, the protocol is guaranteed to be safe as long as honest players hold more than 51% of the stake.

Each slot has a slot leader who oversees adding blocks to the chain and passing them on to the next slot leader. To prevent hostile efforts to undermine the protocol, each new slot leader is obliged to treat the final few blocks of the incoming chain as transitory, with only the chain before the predetermined number of transient blocks being deemed resolved. This is also known as the settlement delay. This means, among other things, that a stakeholder may be offline and still be synchronized to the blockchain, as long as the latency isn’t longer than the settlement delay.

Each network node in the Ouroboros protocol keeps a copy of both the transaction mempool, where new transactions are inserted if they are consistent with current ones, and the blockchain. When a node becomes aware of a newer, more legitimate chain, the locally stored blockchain is replaced.

The disadvantages of Ouroboros Classic were that it was vulnerable to adaptive attackers — a real-world danger that was addressed in Ouroboros Praos – and that there was no safe means for a new member to bootstrap from the blockchain, which is addressed with Ouroboros Genesis.

**Ouroboros BFT**

Following ‘Classic’ was the Ouroboros BFT paper in 2018 (deployed in May 2020). Cardano employed the Ouroboros BFT (Byzantine Fault Tolerance) protocol during the Byron reboot, which was the transfer of the old Cardano codebase to the new. Ouroboros BFT aided in the preparation of Cardano’s release of Shelley, with it, decentralization.

Rather than needing all nodes to be always available, Ouroboros BFT assumes a federated network of servers and synchronous communication between the servers, allowing for easier and more predictable ledger consensus.

Other advantages include immediate evidence of settlement, transaction settlement at network speed (i.e., the speed of your network connection to an OBFT node determines transaction settlement), and instant confirmation in a single round trip of communication. Each of these has a substantial impact on performance.

**Ouroboros Praos**  (current protocol at time of writing, Jan 2024)

The Ouroboros Praos paper was published in 2018 (deployed in August 2020) and is based on Ouroboros Classic, but with significant security and scalability enhancements. Ouroboros Praos, like Ouroboros Classic, divides transaction blocks into slots, which are then aggregated into epochs. Praos, on the other hand, is inspected in a semi-synchronous context and is safe against adaptive attackers, unlike Ouroboros Classic. 

It presupposes two things: that adversaries may transmit arbitrary messages to any participant at any time, and those adversaries can delay honest participant communications for more than one slot. Praos assures that a powerful attacker cannot guess the next slot leader and conduct a targeted attack (like a DDoS attack) to pervert the protocol by using private-leader selection and forward-secure, key-evolving signatures. Praos can also tolerate adversarial controlled message delivery delays and gradual corruption of individual participants in an evolving stakeholder population, which is critical for maintaining network security in a global setting, as long as an honest majority of stakeholder population is maintained.

**Ouroboros Genesis** (paper 2018, not deployed at time of press, but in development)

Ouroboros Genesis was the fourth version of the protocol and built on Ouroboros Praos by including a unique chain selection mechanism that allows parties to bootstrap from a genesis block — without the requirement for trusted checkpoints or assumptions about prior availability. Genesis also proves the protocol’s universal composability, demonstrating that it may be used with other protocols in real world configurations without weakening its security posture. This boosts its security and long-term viability, as well as that of the networks that use it. Genesis is in development and will allow the IOG relays to finally be turned off, which along with the peer-to-peer deployment, will complete the decentralization of the physical network.

Genesis is being implemented by Tweag (*Tweag.io*). Their Director of Engineering gave an explanation of Genesis at the Dubai Cardano Summit

> so it's effectively..if you're concerned about these ...what are called long range attacks. So attacks that would target the chain in the past, with the intent of having an impact on the future... now Ouroboros is is provably secure under certain conditions provided that the nodes are always online, but if a node joins the network, then those those guarantees don't apply, and so Ouroboros Genesis is about saying 'let's allow nodes to not join the network without needing to talk to a trusted relay'... so this is about decentralization

**Ouroboros Peras** will bring fast finality to Cardano. Block finality is about the point at which a block of transactions is considered permanent and cannot be changed or reversed. There is not much more detail about this at time of writing but we should hear more in 2024.

**~~Ouroboros~~ Hydra**

Hydra is an off-chain scaling architecture that tackles three major scalability issues: large transaction output, low latency, and lightweight storage per node. The Hydra whitepaper proposes and details the inclusion of multi-party state channels, which provide parallel transaction processing to greatly boost Cardano’s transaction-per-second (TPS) output, as well as speedy confirmation of transactions. The paper refers to off-chain ledger siblings — state channels – as heads, reflecting the implementation’s namesake. This makes the ledger multi-headed.

Instead of scaling vertically by adding more powerful hardware, Ouroboros Hydra allows Cardano to expand horizontally, enhancing performance by including extra nodes. Early testing indicates that each head is capable of 1,000 TPS. Hydra is being developed in collaboration with the Ouroboros protocol and the Cardano ledger, although it may be used with other systems as long as they have the same properties as Cardano. Hydra was later decoupled from Ouroboros and became an open-source project in its own right. More about Hydra later in Chapter 8.

**Consensus Redux**

The Consensus Redux paper was published August 2020. This paper discusses the concept of a self-healing ledger. How does the ledger recover when it's been attacked? How does a network recover when it's been attacked? The paper outlines solutions in both categories.

**Ouroboros Crypsinous**

The Crypsinous paper was published in 2019 but has yet to be implemented. Crypsinous is the first privacy-preserving proof-of-stake protocol. It boasts increased security features to protect against adaptive attacks including a coin evolution technique based on SNARKS and key-private forward-secure encryption.

**Ouroboros Chronos** (Paper 2021, not deployed at time of press)

Chronos will deliver greater security and network resilience to communication delays by providing more accurate global timekeeping. To maintain the robustness of any dispersed network, global time synchronization is required. Time synchronization is critical in smart contract implementation, from guaranteeing up-to-date information amongst all participants to maintaining correct transaction processing and block construction.

IOG discovered a means to synchronize clocks across a blockchain in conjunction with experts from the Universities of Edinburgh, Purdue, and Connecticut to create a more secure and tamper-proof global time source. This includes time synchronization from internet of things (IoT) devices, such as supply chain monitoring tools, and general distributed systems, especially if a central clock failure poses a security issue. The research is implemented as Ouroboros Chronos (Greek for ‘Time’). 

Chronos is a cryptographically secure blockchain protocol that also offers an accurate source of time thanks to an innovative time synchronization technique that avoids the flaws of externally maintained clocks. This also enables blockchain to precisely time-stamp transactions, making the ledger more resistant to time-based attacks.

By syncing local time to a uniform network clock with no single point of failure, the new protocol may greatly improve the resilience of essential telecoms, transportation, trade systems, and infrastructures. This scientific accomplishment also represents a huge step toward building completely auditable and fraud-proof financial systems by providing exact time and hence full traceability of all transactions. 

**September 22, 2020, re: Chronos.** CH:

> Ouroboros Chronos was a special paper. Leslie Lamport was one of the first guys to do major work in distributed systems and he wrote this beautiful paper on clocks and time in the distributed system from the 1960s or 1970s. It’s one of the most cited papers of all time in the systems world… ‘Time, clocks, and the ordering of events in a distributed system’ and Chronos was like unfinished business in that respect. It’s fun to write papers like that and it has real use. You can completely decouple a dependency on NTP and these types of things, there’s a lot of theory there.

**Timing is everything** 

Within computer systems and applications, the idea of time is critical. You wouldn’t be able to access any transport layer security (TLS)-based websites, exchange data, or use other cryptographic techniques without this notion.

Time tracking, on the other hand, is a challenging issue to tackle. Accurate time synchronization requires data transfer throughout the whole internet, which costs time as well. It’s also difficult to forecast how long a particular data transfer will take since the network status is continually changing and is influenced by variables like congestion and data size, among others. As a result, discrepancies are common, and it’s critical to supply the tools and solutions necessary for accurate timekeeping.

It’s easy to take timekeeping for granted with basic PCs. Behind the scenes, however, there is a strict protocol to follow. The Network Time Protocol (NTP), for example, uses a worldwide hierarchy of servers to solve the timekeeping problem. This comprises up to 15 Stratums, each with its own routing designed to synchronize in the most efficient way possible. The development of a Bellman-Ford shortest-path spanning tree, which reduces latency and transmission time inconsistencies, also helps.

**Time synching on the Blockchain** 

For distributed ledger technology, the idea of timekeeping is different. The network cannot verify that a transaction being processed is genuine, and does not reverse the prior one, without a correct timestamp. Different timestamping algorithms are employed across a variety of blockchain ledgers; however, they aren’t always reliable. Bitcoin, for example, employs timestamps for consensus security but not for timekeeping.

Timekeeping is also necessary for smart contract execution. Decentralized finance (DeFi) smart contract attacks are vulnerable to inaccuracy. Vulnerabilities in smart contracts aren’t necessarily caused by bad code; time discrepancies should be fixed to prevent any potential attacks on the ledger. Some blockchains, such as Solana, have experienced critical ‘clock drift’ issues.

**Time for reflection**

Building complex trading platforms, such as Axo (axo.trade), is not trivial when calculating exact times on a decentralized blockchain. The topic has been debated in IOG’s blogs, in the docs and more heatedly on twitter.  Although Cardano's current measure of time appears satisfactory to cover many use cases, it is not perfect. To dive deeper into the technical minutiae, it’s best to take in the views of several experts. Axo chief Jarek Hirniak, an experienced developer in trading software, wrote *Time on Cardano*, while Sebastien Guillemot has covered ‘timing’ comprehensively in several of his YouTube videos.

**December 12, 2020. Is Chronos implemented?** CH:

> We'd like to be reliant on nothing and no one, and as decentralized as possible. So, we were the first to address this in the very first paper of its kind, with something called Ouroboros Chronos, but it would be an unnecessary diversion to just go and chase 3 months of implementation to pull Chronos in, when we don't need it as a system right now. […] 
>
>The other thing is that Chronos should be implemented with Consensus Redux, should be implemented with Genesis, and should be implemented with fast finality. and high throughput enhancements to the system, so Ouroboros 2 (subsequently named Ouroboros Omega) is a rollup of all the research that we've done which will make it considerably better than anything in market. So, the name of deployment execution is saying ‘what is a problem today? What's a theoretical but unlikely issue? Versus what is a practical and certainly problematic issue to resolve?’ …and understand how to balance things and create a roadmap accordingly.

**Ouroboros Leios**

The Leios paper was published in November 2022 and is surprisingly readable. It was previewed in this video by Professor Aggelos Kiayias. The focus of Leios is Input Endorsers which leverage the aforementioned foundational Ouroboros functionality as well as Mithril (See Chapter 8). As input endorsers are quite technical and based on concepts not discussed yet, they are covered in the last section of *Chapter 8, Basho (Scalability)*. From section 6.2 of the paper:

> Just as Ouroboros Praos+Genesis is a valid combination, Ouroboros Leios+Genesis makes perfect sense too and provides the same benefits. Thus in some sense Leios and Genesis are independent features. In practice Genesis will be deployed by the time that Leios is available and so it would be a regression if the Genesis feature were not included.

**Ouroboros Omega** will be the capstone of all the proof-of-stake research IOG have accomplished since 2016. There should be a paper soon on the ‘convergence of all the ideas.’ 

**February 9, 2021. Can you talk about Ouroboros Omega?** CH:

> Omega is the culmination of all of our research of the last 6 years for Ouroboros: no reliance on external clock, self-healing so it can gradually recover 51% attacks, the ability to bootstrap from Genesis, semi-synchrony, adaptive security, instant finality… all kinds of stuff…multi-validation per block… there's so much stuff …. Things like the consensus Redux paper, the Ledger Combiners paper … the Chronos paper, the Genesis paper, the Praos paper and then all the theory and then some of the engineering acumen, including an improvement to about a thousand TPS (transactions per second). 

## How the Consensus Layer Works

Abstraction is a key feature of the consensus layer.

The Cardano consensus layer is responsible for two major duties:  
 
1. It uses the blockchain consensus mechanism to keep track of transactions. Consensus, or ‘majority of opinion,’ in the context of a blockchain, implies that everyone participating agrees on the one true chain. This means that the consensus layer is responsible for accepting blocks, selecting between rival chains if any exist, and determining when to create its own blocks.

2. It is in charge of preserving all of the information needed to make these judgments. The protocol must verify a block in relation to the state of the ledger before deciding whether to accept it. It must preserve enough history to be able to rebuild the ledger state on a different chain (a different point of a fork in the chain) if it chooses to move to a different chain. It must maintain a mempool of transactions to be placed into those blocks to be able to create blocks.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/node.png "Cardano Node") 

Figure 4.1:  Cardano Node component parts, drawing by @_ktorz_

The Cardano node is made up of several interconnected layers:

- The networking layer is based on a P2P (peer-to-peer) networking stack tailored to Ouroboros consensus protocol. This includes a framework which supports pipelining, multiplexing and various protections against adversarial peers.

- The consensus layer is an implementation of the Ouroboros family of protocols. 

- The settlement layer is a multi-era ledger implementation derived from formal specifications. This is where the core Cardano entities are defined as well as the rules for using them. This is the bedrock on top of which consensus and networking are built upon. The settlement layer is completely stateless and only contains pure functions. As a result, it isn’t necessary for the consensus layer to understand the precise nature of the ledger state, or even the contents of the blocks (apart from some header fields required to run the consensus protocol).

- The scripting layer, Haskell code on the Plutus Platform (subject of a later chapter) is a scripting language embedded in the Cardano ledger to provide smart-contract capabilities to the network. 

**Consensus Roles**

The consensus protocol has three major roles: 

1. Leader check (who should produce a block?)
2. Chain selection
3. Block verification

The protocol is designed to be independent of a specific block or ledger, allowing a single protocol to be used with a variety of blocks and/or ledgers. As a result, each of these three roles establishes its own ‘picture’ of the data.

Every slot has a **leader check** that determines whether the node should create a block. In practice, the leader check may need the extraction of certain information from the ledger state. The chance of a node being elected as leader (authorized to generate a block) in the Ouroboros Praos consensus protocol, for example, is dependent on its stake, the node’s stake. 

The process of selecting between two competing chains is known as **chain selection**. The chain length is the most important selection criteria here, however other protocols may have extra requirements. Blocks, for example, are usually signed using a ‘hot’ key that lives on the server and created by a ‘cold’ key that never appears on any networked device. If the hot key is compromised, the node operator may create a new one using the cold key and ‘delegate’ to it. A consensus protocol will favor the newer hot key over two chains of similar length, ie. Each chain includes a tip signed by the same cold key but a different hot key.

**Block validation** is primarily a ledger problem; checks such as ensuring all transaction inputs are accessible to prevent double spending are specified in the ledger layer. What’s within the blocks is mainly unknown to the consensus layer; in fact, it may not even be a cryptocurrency, but a distinct use of blockchain technology. IOG used the example of a Pokémon ledger on Ouroboros previously. However, block headers include a few items that are expressly designed to aid the consensus layer.

**Node configuration**

To execute, each protocol may need certain static data, such as keys to sign blocks, a unique id for the leader check, and so on. This is referred to as the ‘node configuration.’

**The ledger state**

The consensus layer not only handles the ledger state but also operates the consensus protocol. It is unconcerned with the look of the ledger state; instead, it assumes that some form of ledger state is connected with a block type.

If a block is invalid, you may get an error while applying it to the ledger state. The ledger layer defines the precise kind of ledger errors, which are ledger specific. The Shelley ledger, for example, will have staking errors, but the Byron ledger would not since it does not enable staking; and ledgers that aren’t crypto ledgers will have quite different errors.

The Cardano consensus layer was created with the Cardano blockchain in mind, which initially ran Byron and was updated to run Shelley. It’s fair to ask why didn’t IOG developers create for that particular blockchain first? Then generalize when utilizing the consensus layer for other blockchains? However, there would have been significant drawbacks in doing so:

- It would obstruct IOG’s capacity to conduct tests. They wouldn’t be able to choose which nodes create blocks when, they wouldn’t be able to use a dual ledger, and so on

- It would entangle things that should be logically separate. The Shelley ledger, in the abstract method, is made up of three parts: a Byron chain, a Shelley chain, and a hard fork combinator that connects the two. Without abstractions, such separation of concerns would be more difficult to establish, resulting in code that was more complex to comprehend and maintain

- Abstract code is less likely to include flaws. For example, since the dual ledger combinator is polymorphic  in the two ledgers it combines, and they are of different types, IOG couldn’t construct type correct code that attempts to apply the main block to the auxiliary ledger

- When the time inevitably comes to instantiate the consensus layer for a new blockchain, writing it in an abstract manner from the start forces IOG to think carefully about the design and avoid coupling things that shouldn’t be coupled, or making assumptions that may or may not be true in general. It might be difficult to fix such issues once the design has been implemented.

To achieve all of this, a programming language with exceptional abstraction capabilities is required, and Haskell is well equipped in this regard.

**January 10, 2021. Please explain Cardano being 100x more decentralized than BTC or others, how is this calculated?** CH:

>It’s calculated by those who produce blocks, so if you have a hundred times the unique entities producing blocks, then we say it’s a hundred times more decentralized, but there are many measurements of decentralization. You can look at network propagation, so how many full nodes you have. You can look at unique development entities responsible for it …you can look at the funding sources and see how many unique funding sources are there. You can see the totality of the user count…
>
>You can see it by the total applications on the system but usually when we say decentralization, we strictly mean the amount of nodes participating in the consensus process and how many unique people are making blocks. In the case of bitcoin, 3 to 5 usually make the same blocks again and again… and we consistently have 300 to 500 stake pools consistently making blocks that are unique. There’s over 1200 registered (currently over 3,000), so I feel very comfortable in the 100x statement, but reasonable people can have different definitions, there’s no consensus in the industry of what decentralization is.

## Hard Forking Business  

In the context of the blockchain, a ‘hard fork’ refers to a significant change in the chain, such as switching from one protocol to another. A hard fork in most blockchains denotes block modifications or a change in their interpretation. Typically, when a hard fork is performed, the existing protocol is turned off, new rules and modifications are introduced, and the chain is restarted. A hard-forked chain will be distinct from the prior version, and that the pre-forked blockchain’s history will no longer be accessible.

The Cardano blockchain has hard forked from a federated Byron model to a decentralized Shelley model. This hard fork, on the other hand, was one-of-a-kind. IOG guaranteed a seamless transition to a new protocol while maintaining the history of earlier blocks, rather than making major modifications, the chain did not alter drastically. Instead, it included Byron blocks before adding Shelley blocks after a transition time. There was no ‘turning it on and off again’. The entire history was retained. There has been no downtime or restarts with Cardano, which is not always the case with other chains.

**Hard Fork Combinator**

In Cardano docs and blogs, you may have seen a hard fork referred to as an ‘HFC’ or a ‘HFC event’. A combinator is a technical term that refers to the joining of two or more processes. In the context of Cardano, a hard fork combinator combines protocols, allowing the Byron-to-Shelley transition to be completed without the need for a system restart. It guaranteed that the ledgers of Byron and Shelley display as a single ledger. It was not necessary for all nodes to update at the same time when switching from Ouroboros BFT to Ouroboros Praos. Instead, nodes updated in stages; some running Byron blocks, others running Shelley blocks.

The hard fork combinator is intended to allow the integration of many protocols without requiring major changes. Byron and Shelley blocks are now combined in the Cardano chain. For future ‘hard fork events’, Basho and Voltaire blocks will be combined as well - all as a single property. By simplifying the prior Byron-to-Shelley evolution, this (HFC) hard fork combinator also made the transfer from Shelley to Goguen seamless with gradual, iterative upgrades rolled out as the Allegra, Mary and Alonzo updates. 

**HFC history to date** 

The Cardano platform entered a rapid development phase with the introduction of the Incentivized Testnet in 2019, which marked the beginning of the Shelley era. The Ouroboros Classic consensus system previously supported Byron and ada, and subsequently migrated to Ouroboros Praos. As Cardano decentralized, this was the version of proof-of-stake (PoS) protocol that first powered Shelley. It incorporated monetary rewards into the staking procedure for ada holders and stake pool owners.

In February 2020, IOG upgraded Cardano with a hard fork that moved the mainnet from Ouroboros Classic to Ouroboros BFT, an enhanced version of the original consensus mechanism. This BFT hard fork kicked off a transition phase under Ouroboros BFT, a pared-down version of the protocol aimed to ease the transfer to Praos while still avoiding malicious behavior. Users were unlikely to have noticed. It meant a routine software update for Daedalus wallet users. Exchanges were required to update manually, but they had many weeks to do it and IOG were available to assist.

The ‘Byron reboot’ followed that in March 2020. Many Cardano components received completely new code, including a new node to handle delegation and decentralization, as well as future Shelley features. The new code base was redesigned to be modular, which meant that many components could be updated without impacting the others.

In turn, the BFT served as a springboard for the Shelley hard fork, which happened after the Haskell testnet was complete. For exchanges, ada holders, and wallet users, this second hard fork was similar to the first, a non-event in terms of user disruption. However, although everything seems to be in order on the surface, there was a lot of activity going on behind the scenes. IOG’s developers were hard at work making it a seamless, benign experience for the end user. IOG chief architect Duncan Coutts explained at the time:

>IOG’s blockchain engineers believe in smooth code updates. Instead of trying to do the jump from Ouroboros Classic to Praos in a single update – which would be an incredibly complex task – it’s been a two-stage approach using Ouroboros BFT as an intermediary. The BFT code is compatible with both the Byron-era federated nodes and the Shelley-style nodes released in the Byron reboot. It’s like a relay race: one runner (in our case, running one protocol) enters the handover box where the other runner is waiting; they synchronize their speeds (so they’re perfectly compatible with each other) and then hand over the baton (operating the mainnet), and then the new runner with the baton continues from the handover box for the next lap.

IOG were able to swiftly design and test a new wallet using Daedalus *Flight*, and once everyone was using it on the mainnet, and IOG finished changing over the core nodes, the old code was obsolete. *Flight* is IOGs version of Chrome Canary for Daedalus.

In summary, the only real hard fork for Cardano was the switch from Ouroboros Classic to BFT (February 2020). The Byron mainnet was relaunched to run the BFT protocol, allowing for a smoother transition to Ouroboros Praos with fewer chain disruptions. The BFT protocol was meticulously built to preserve blockchain history and make the blockchain look as a single entity.

As IOG chief executive Charles Hoskinson discussed in his whiteboard video about the hard fork, the goal was to have a ‘graceful entry into Shelley.’ The hard fork combinator was crucial in accomplishing this transition. 

**Goguen Era Updates**

**Allegra (Token Locking)**

Token locking was a feature introduced to the Shelley protocol to allow a variety of smart contract use cases, such as generating and transacting with multi-asset tokens and adding support for the Voltaire voting mechanism. Token locking is the act of reserving a certain number of assets and agreeing not to sell them for a given length of time. This functionality was enabled in the *Allegra* upgrade in December 2020. *Allegra* was named after Allegra Byron, Lord Byron’s daughter and sister to Ada Lovelace. 

Token locking allowed for more complicated deal settlement and fund accounting. It’s used in the following scenarios:

- **Contractual agreement** - when someone engages into a contractual agreement, such as to sell an asset like a painting, it is essential to guarantee that the painting will not be sold to anyone else save the person who pays the money. The token may represent both the painting and the ‘promise’, the actual token locking in this example. The contract becomes invalid if the painting is sold to a different third party

- **Vote registry** - Token locking allows users to lock a set quantity of their tokens to reflect their voting rights inside the Voltaire voting system. Holders of ada tokens who participate in the voting process must ‘lock’ their tokens. This will reflect their voting rights in proportion to their investment and will prevent the hazards of double-counting votes, awarding more votes than is feasible, contradicting votes, or vote duplication

- **Multi-asset tokens** - In addition to ada, Cardano allows for multi-asset tokens, with the ledger supporting the creation and usage of several bespoke token types. Token locking enables ada tokens to be ‘locked’ to create a bespoke asset of equal value.

**Mary (multi-asset support)**

This then paved the way for the *Mary* (multi-asset support) upgrade in March 2021. It was named after Mary Shelley (the author and wife of Shelley). MAS (multi-asset support) means you can record that a particular token is being used for a specified purpose. The token may represent any object that is recorded on (native to) the blockchain ledger, such as ada, and other custom tokens. *Mary* enables users to generate (custom) tokens with unique characteristics and conduct transactions with them directly on the blockchain.

The ledger’s accounting architecture now handles not just ada transactions, but also transactions that hold several asset types at the same time. Developers benefit from native support since they don’t have to write smart contracts to handle bespoke token minting or transactions. Instead, the accounting ledger keeps track of asset ownership and transfers, minimizing unnecessary complexity and the risk of human error while also ensuring considerable cost savings.

To fulfill commercial or business goals, developers, enterprises, and apps can build general purpose (fungible) or specialized (non-fungible) tokens. Custom payment tokens or rewards for decentralized apps, stablecoins pegged to other currencies, and unique assets that represent intellectual property are just a few examples. All of these assets may then be traded, swapped, or used to purchase goods and services.

**Alonzo (smart contracts)**

Still part of the Goguen era, *Alonzo* was the next protocol update in Sept 2021. To enable functional smart contracts, *Alonzo* built on top of transaction metadata, token locking, and native asset functionality. By allowing the development of smart contracts and decentralized apps (dApps) for DeFi (decentralized finance), this update created a diverse platform that opened up options for enterprises and developers.

This functionality is available and enabled by the tools and infrastructure that make up the Plutus Platform. *Alonzo* enhanced Shelley’s basic multi-signature (multisig) scripting language with a rigorous methodology based on formal methods and verification. For more sophisticated and secure scripting capabilities, Multisig was updated into the Plutus Core language. *Alonzo* enables this through extended unspent transaction output (eUTXO) accounting. More on this later.

*Alonzo* was named after Alonzo Church (1903-95). Church was a logician and mathematician who worked on logic and the foundations of theoretical computer science in the US. He is also recognized for establishing lambda calculus, a formal system that may be used to argue that the Entscheidungsproblem is unsolvable. Later, when working with Alan Turing, they realized that the lambda calculus and the Turing machine had equivalent capabilities, displaying numerous mechanical computing processes. Plutus Core (Cardano’s smart contract language) is a variant of lambda calculus, which is one of the reasons for naming the smart contract upgrade after Church.

**Vasil**

Named after a Bulgarian mathematician Vasil Dabov, who was also a Cardano community member, the Vasil hard fork in Sept 2022 brought five key features to boost performance. These were mainly focused on Plutus V2 after CIPs (Cardano Improvement Proposal) were submitted by the community. CIP-31 (Reference Inputs), CIP-32 (Inline Datums), CIP-33 (Reference Scripts), CIP-40 (Collateral Outputs), and diffusion pipelining are discussed later.

The terminology and the use of the same terms in different contexts can get quite confusing. Fear not, as there is page the documentation explaining the difference between an ‘era’ and a ‘phase’, and how a ‘hard fork’ differs from an ‘intra-era hard fork’. Starting with Alonzo, the ‘ledger eras’ are named after mathematicians and computer scientists, kind of like the hurricane naming system but in alphabetical ordering. The release dates are named in honor of Cardano community members.  

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/eras.png "Cardano Eras")

**Figure 4.2:**  Cardano Phases, eras, and intra-era hard forks  

The SECP update in Februrary 2023 was executed as an ‘intra-era hard fork’. This brought new cryptographic primitives to Cardano. More about this update in chapter 6.

**June 5, 2020. What is the best code in Cardano?** CH:

> The hard fork combinator code is the second most elegant code we have; the most elegant code belongs to the network code. We have lots of crazy stuff there, very elegant, very academic scary code …but beautiful.

## Path to Full Decentralization

Cardano hit a milestone at the end of March 2021 when *d*, the parameter that determines what proportion of transactions are processed by the genesis nodes, reached zero. The duty for block creation was totally decentralized at this time. Cardano’s network of 1,800 (March 2021) community pools were fully responsible for the generation of blocks.

The day *d* reached 0 was a watershed point for Cardano. When IOG released the Shelley update in July 2020, they set *d* to 1.0, which meant that every block was generated by IOG’s federated nodes. Of course, this was the opposite of decentralization, but it was a prudent (secure) strategy in the short term until the stake pool operator (SPO) network was set up and mature.

IOG steadily lowered *d* at a rate of 0.02 each epoch over time, an increase of two percentage points in community block production every 5 days. When *d* dropped, the community created more blocks, and more stake pools were able to generate blocks. The network’s diversity and geographic dispersion grew as *d* decreased.

*d* hit zero on March 31, 2021, at the end of epoch 257. That day was memorable because, although *d* is a modest number, its importance is enormous. That zero was the most crucial external signal of decentralization, a parameterized symbol confirming a major principle of Cardano’s ideology of pushing power to the edges.

**Trickier parameter adjustments**

> Setting stable parameter settings, while still being flexible for the future, is critical to Cardano’s continued development and decentralization. While the transitioning the d parameter was smooth and predictable, changing other parameters requires a more nuanced approach. IOG consulted with the community before setting initial values. Around 20 parameters regulate network behavior, and settings had to be specified for all of them before the mainnet could be launched. The majority of these parameters are technical in nature, so although they must be set appropriately to ensure system safety and improve performance, their specific values have little impact on user experience. You can review the full list of current parameter settings on ADApools.org. 

**June 4, 2019. Re: Ouroboros parameters.** CH:

> What is the protection mechanism against too many stake pools? So, you have to delegate to the stake pools …so there’s only a finite amount of ada and the financial incentives are basically set up in a way where you will have a ceiling of stake pools, and if you have more than that, you actually make less money. So, I’d highly encourage you to read our paper, we wrote out of Oxford with Alexander Russel. The paper covers how you parameterize that model and that’s why we can believe that there’ll be a stable thousand stake pools after a while.

**K = number of stake pools**

A crucial element is the desired number of stake pools, or the k parameter. *k* is the reward scheme parameter that determines the soft limit on the pool size. Cardano incentives have been intended to foster an equilibrium with *k* completely saturated pools, which means that when all stake is delegated equally to the *k* most appealing pools, rewards will be optimum for everyone. At equilibrium, assuming rational participants and no external influences, the mechanism is constructed such that the stakeholders’ optimal response behavior converges to *k* pools of equal size, each delivering the same amount of rewards per unit of stake to their delegates.

The greater the value of *k*, the more decentralized the system. More *k*, on the other hand, results in a less efficient system (higher expenses, greater energy consumption) and fewer returns for both delegators and stake pool owners. IOG knew that the community would be motivated to build up pools based on what IOG learnt from both the Incentivized Testnet (ITN) and the Haskell Shelley testnet.

Decentralization occurred fast but decentralization alone is insufficient. Cardano requires long-term commitment from its operators, and operators must be appropriately rewarded for continuing to sustain the system. The initial proposal was k=150 for the mainnet deployment of Shelley, to be progressively raised to create a balance between decentralization and rewards for stake pool managers. This was a little improvement over the parameter choice in the incentive testnet (ITN), which was k=100. This was seen to be a cautious approach at the time, aimed to enable a seamless transition of the ITN environment to the mainnet. This guaranteed that the system was stable and efficient at first and could progressively evolve over time to become more decentralized, and secure, in the future.

Cardano is an order of magnitude more decentralized than any other blockchain due to *k* stake pools of roughly similar size. And this was only the start. Tiny, progressive increases in the *k*-parameter aren’t possible (unlike, for example, the decentralization *d* parameter, which lent itself to a gradual reduction). Each rise in *k* necessitates action on the part of pools and delegators. For pool operators, this entails fine-tuning their settings, particularly their margin; for delegators, it entails selecting new pools to delegate their ada to, particularly if their existing selection becomes oversaturated.

As a result, the optimal method for increasing *k* is to do it in bigger, less frequent increments – and as quickly as realistic network dynamics and economics will allow. The optimum option is one that causes the least amount of disturbance to successful pools and their delegators while increasing the chance for medium and smaller pools to mint blocks and attract additional stake. It’s also critical to have a long-term strategic aim in mind as a community: to spread decentralization as broadly as possible.

**The *k* = 500 change**

At epoch 234, an adjustment to *k*=500 was made on December 6, 2020. Small-to-medium-sized pools that were having trouble attracting delegation benefited from the change to *k*=500. It also restricted pool size to 64 million ada, meaning that more than 100 of the biggest pools would overfill.

It’s always best practice for delegators to monitor their preferred pools. You should redelegate if you see your chosen pool becoming oversaturated. It’s crucial to remember that rewards will still be paid out from relatively saturated pools, but they’ll decrease when the pool’s saturation rises. No one who delegated to an over-saturated pool ever lost any ada. It’s only that if one remains in a saturated pool, the return on investment will be diminished.

**Monetary Policy**

Transaction fees and monetary expansion are used to fund staking rewards for both delegators and stake pool operators. Every epoch, all transaction fees from all transactions from all blocks created during that epoch are collected and placed in a virtual ‘pot.’ A predetermined proportion of the leftover ada reserves, *ρ*, is also contributed to the pot. Then a portion of the pot, *τ*, is paid to the Treasury, and the remainder is used as epoch rewards. *ρ* (Rho) and *τ* (tau) are letters of the Greek alphabet…the chief scientist at IOG, Prof Aggelos Kiayias, is Greek which might explain the naming policy. 

This approach guarantees that the share of rewards taken from the reserves is large in the beginning, when the number of transactions is still relatively modest since users are only starting to create their businesses on Cardano. Early adopters will be enticed to act swiftly to reap the benefits of the high initial payouts. The higher costs compensate for declining reserves over time as transaction volume grows.

This technique also guarantees that the rewards provided are predictable and evolve over time. There will be no ‘jumps’ like the bitcoin halving occurrences that occur every four years. Instead, a steady exponential fall is guaranteed by a predetermined proportion deducted from residual reserves every epoch.

So, what kind of value should *ρ* take? What percentage of the budget should go to the Treasury? This is also another trade-off: larger values of *ρ* indicate bigger rewards for everyone at first, as well as a faster-filling treasury. However, greater levels of *ρ* imply a quicker depletion of reserves. Paying big incentives and incentivizing early adopters is crucial, however, it is equally critical to present all stakeholders with a long-term view.

Cardano will never run out of reserves; instead, it will be an exponential decay. Calculate the ‘reserve half-life,’ or the time it takes for half of the reserve to be used up, to obtain a sense of the effect of a certain value of *ρ*. After careful consideration, 0.22% was the proposal for *ρ*. When the numbers are crunched, the ‘reserve half-life’ comes out to be roughly 4 to 5 years. In other words, half of the remaining reserve will be consumed every four to five years. Because this is near to the four-year ‘bitcoin half-life,’ Cardano holdings will diminish at a similar pace to bitcoin reserves.

It’s worth mentioning that Bitcoin took almost eight years to attain its highest level of popularity and pricing. As a result, it is reasonable to anticipate Cardano transaction volume and exchange rate to rise substantially over the coming years to more than compensate for the reduction in monetary expansion.

**Funding the Treasury**

IOG also recommended a starting figure of 5% for *τ*, the proportion of rewards that are automatically sent to the Treasury at the end of each epoch. Over the following five years, at least 380m ada will be transferred from the reserves to the Treasury.

The actual amount coming to the Treasury will be much larger. To begin with, it’s unrealistic to anticipate that all ada will be delegated based on learnings from the Incentivized Testnet, but also anticipating future usage of ada. Some of it will be stored on exchanges, traded, and used in smart contracts. Unclaimed rewards will result from the ada that is not delegated. The treasury will salvage these unclaimed rewards.

It’s not expected that pools’ pledges will be overly large, just high enough to make launching a Sybil attack undesirable. The difference between prospective pool rewards with a very high pledge and pools with a more realistic pledge level, ends up in the treasury as well. For the foreseeable future, the total of all ada going to the Treasury indicates that there will be enough funds to pay for new features and upgrades.

**Pledge Influence Factor (a0)** 

The ada pledged by pool owners protects against Sybil attacks by ensuring that delegated stake is not overly drawn to pools whose owners attempt to abuse the system by forming multiple pools without owning a substantial amount of stake themselves. There was a lengthy debate, at the time, on this episode of the Cardano Effect. The debate has continued for some time about why, how and by whom, the parameters should be adjusted. Umed Saidov (who wrote this analysis in 2020) and ‘Big Pey’ laid out their case for change in this passionate discussion at the *Rare Bloom* event. 

The pledge influence factor has a direct impact on a pool’s rewards: the higher the influence factor, the greater the impact of a bigger pledge on rewards. A greater influence factor improves Sybil protection and makes the system safer and more secure, but it also offers stake pool owners who can afford a bigger pledge an advantage.

The initial value of 0.3 was intended to strike a compromise between the amount of Sybil protection and the pledge needed. However, there is no minimum pledge. The pledge may be made as low or as high as the pool operator decides. Their choices impact the rewards, but there is no ‘hard’ rule requiring them to pledge a certain amount. This means that pool pledges will eventually go as high as pool owners are willing to go, and it will be up to the community to strike a balance between security, economic concerns, and the desire for justice and equal opportunity.

**Pledge deferred update**

SPOs that concentrate their pledge into a limited number of pools are rewarded with the *a0* parameter. This has worked well in encouraging pools with high levels of ada pledge to combine into big private pools (like IOG do), giving smaller pools a better chance to recruit delegators. However, IOG felt the existing method could be improved, therefore debated and modeled ideas to make pledge more successful at resolving pool splitting for lower pledge levels. 

While there has been much internal debate, IOG came to the conclusion that any change in *k* should be only made after revising the formula for *a0* to get the desired outcomes (especially encouraging stake to flow to smaller single pools rather than split pools). Because this was a complete formula change rather than just an epoch boundary change, it had to be issued as part of a hard fork. IOG planned to make this adjustment for some time but given their product pipelines and their team’s focus on the Goguen rollout, the update has not occurred yet and pledge influence factor *a0* remains at 0.3.

**As things stand (Jan 2024)**

Different parameters are used to as lever to control Cardano’s protocol behavior. Some parameters are predictable and go unnoticed and largely left alone. Others are more prominent as they directly impact on-chain activities and need regular tuning as the protocol moves out of testnets and hard forks change the playing field conditions for stake pool operators and delegators. 

Two variable parameters continue to divide opinion among the SPOs community as they relate to the core principle of Cardano, decentralization, and they impact their ability to earn a living. These are the *k* value (the number of stake pools who receive rewards), and the minimum pool fee, which is a set amount paid to a pool before rewards are split with delegators.

*k* (currently 500) impacts the max pool size, based on the equation: = (45bn - reserves) / *k* = ( 35bn / 500 ) = 70m

IOG conducted a community survey to ‘read the room’ but there was not consensus on what changes to make, or how to implement them. IOG previously proposed raising *k* to 1000, but this was postponed as the survey was not clear cut, IOG were busy with the Vasil hard fork and it was decided more planning and discussion was required.

The MinPool fee has also been an emotive topic. SPOs are the engine room for Cardano operationally. They produce new blocks and ensure a decentralized network grows. They are paid for their work in two ways:

- a fixed fee, a set amount taken if blocks are produced, and
- a variable fee, a percentage of the total rewards paid to a pool. 

Staking pools can chose to set any variable fee they like, but the ledger rules has a *minimum* fixed fee in place. This was there originally as defence against Sybil attacks (an adversary might hijack the network by creating a lot of zero-fee pools). Many feel this protection is no longer needed, including IOG who admit this risk may be a more theoretical than practical at this stage as delegation is so decentralized. 

A big reason to reduce, or remove it, is it is an obstacle for small new pools to compete with the bigger, more established stake pools. This can be a double whammy as the minimum fee can also incentivize larger SPOs to create new pools since there is a guaranteed profit from doing so.

To get a sense of how emotive these issues are, you should listen to the Twitter Space hosted by Bullish Dumpling and read Adam Dean’s twitter thread. *Army of Spies* dedicated a video to it and IOG have written a blog post mapping out potential courses of action. We haven’t even mentioned CIP 50 (Liesenfelt Shelleys Voltaire Decentralization Update) which is worthy of a book in itself. I suspect these decisions are deliberately being left to test-drive the new on-chain governance mechanisms. These new levers of power are explored in Chapter 9. Charles Hoskinson all but confirmed this on a recent AMA: 

> It's not about IOG changing parameters, the system is stable at the moment, it would be nice to get all the parameters and tune them on a regular basis, but that's the entire point of CIP 1694. You guys should be doing that. If you want to sign up and have a custodian sit down and think about how to tune the system every month, so that it promotes some outcome, I think that's not the point of Cardano, the point of Cardano is the Cardano community self-regulates Cardano. So what we did is we got the system to a stable state, with that stable state it's able to survive and thrive, the next step is to get the community to take that stable state and create a government on top of it. So if you want to change the system parameters, then go ahead and get something like CIP 1694 in. Obviously, there'll be some fine tuning throughout this year, there's some final things to do as things change, as peer-to-peer gets fully implemented and Genesis gets fully implemented, but it defeats the entire purpose of decentralization to have a tuning committee that's federated

In May 2023, the Cardano Foundation conducted a SPO on-chain poll, a new mechanism (defined in CIP-94) to allow stake pool operators to vote on crucial issues based on the stake delegated to their pool. Shortly after the poll, ‘minPoolCost’ was subsequently cut to 170 ada. It was decided it would be risky to change the *k* parameter at the same time. More about the governance around protocol updates in Chapter 9. 

## Ouroboros lays the foundation for the Basho Era

Considering all the features and functionality introduced by the hard forks we just talked about, it's not a surprise that network activity would pick up, but Cardano’s design will enable it to bend and adapt as needed.

**Network bandwidth**   

All Cardano activities are built on top of networking. The Cardano network distributes transactions and blocks among nodes all around the globe that build and validate the blockchain. This is known as data diffusion, and it is necessary for the consensus protocol to make judgments by providing the necessary information to nodes. These choices move the chain forward, since node consensus guarantees that all transactions are confirmed and approved, allowing them to be included in a new block in a transparent manner.

The speed with which the system as a whole operates is influenced by network performance. This covers things like:

- *throughput* (amount of data transferred)
- *timeliness* (time for block adoption)

These two needs are in direct opposition to one another. When the created blocks are used as effectively as possible, throughput can be increased. This, in turn, requires adequate buffering to offset latency, reducing the negative effects of a globally distributed system. When the system is saturated, more buffering may frequently suggest greater block (and network) usage, but it comes at the expense of higher latency (time to adoption in the chain).

**A block’s budget**

To comprehend how quickly Cardano transactions and scripts may be completed, the concept of the block budget is key. A block’s total size strikes a balance between maximizing network use and reducing transaction latencies. A single block may include a variety of transactions, including smart contracts written in Plutus, native tokens, metadata, and straightforward ada transactions (payments).       

Another attribute is the block time budget, which is a set amount of time allowed to complete all of the transactions in a single block. This is split between the amount of time available for Plutus script execution and the amount of time available for other transactions. This attribute guarantees that transactions containing Plutus scripts do not consume the available time budget, and that basic payments may always be processed in the same block as Plutus scripts. 

The entire time budget for creating each block (including networking overhead) is set to 1 second, with a Plutus script execution budget of around 50 milliseconds. This is a reasonable provision; IOG’s testing has demonstrated that many scripts on a testing environment will run in 1 millisecond or less.

The block time budget was set initially at 1 second. Due to security concerns, the Praos consensus process picks just a small proportion (1 in 20) of the blocks that might possibly be added to the chain. Obviously, the size and effective payloads of various transactions will change. A single transaction, for example, may close off an entire Catalyst voting round, moving millions of dollars in value.

As previously stated, each block contains a number of transactions submitted by end users through wallets, the command-line interface (CLI), and other means. These transactions are stored in the mempool, a temporary in-memory storage space, until they are ready to be processed and included in a block. As a block is minted, pending transactions are removed from the mempool, allowing new transactions to be added. The potential of nodes being overwhelmed during high-demand times was eliminated by employing a fixed-size mempool, although this meant that a wallet or application may have needed to re-submit transactions. The mempool size was determined using queueing models.

**Stress testing the network**

Ouroboros is built to manage massive amounts of data, as well as transactions and scripts of various sizes and complexity. With the settings in place the Cardano network was still only using around 25% of its capacity on average in October 2021. Of course, the most efficient option is for Cardano to operate at or near 100% capacity (network saturation). While many networking systems would suffer in such circumstances, Ouroboros and the Cardano network stack have been engineered to be fair and very durable even in the face of extreme saturation. 

Benchmarking data reveals that even at 200% saturation, overall performance remains stable, and no network failures occur. Even with stress tested at 44x, there were no problems in the entire network capacity (though some transactions may be slightly delayed). Backpressure is used to regulate the overall system load, which is how the network is meant to function. 

While certain users participating in a big NFT drop may suffer lengthier wait times for their transactions or may need to resubmit the rare transaction from a large batch (or spread the drops over a longer time period), this does not indicate that the network is not coping. It really signifies that the network is working properly. It’s referred to as ‘graceful degradation,’ and you can understand in more detail by reading the network design paper. See ‘Cardano Upcoming NFT drops.’

**Wallet types**   

End-user wallets submit payments and other transactions to the blockchain on their behalf, as well as monitor the blockchain’s progress. One of the most important functions of a wallet is to submit transactions on behalf of the user, validate that they have been approved into the blockchain, and retry them if the first attempt fails. That is, when the network saturates, the wallet should consider the implications of backpressure as well as other network effects (temporary disconnection, possible chain forks, etc). Wallets may be one of two types:

- Full-node wallets (like Daedalus), which operate a node that connects directly to the Cardano network using local compute and network resources

- Light wallets, on the other hand, take advantage of pooled processing and networking resources to service a large number of users.

Both kinds of wallets may need to retry transactions during times of strong demand (e.g., an NFT drop). Light wallets may need to temporarily scale available compute and network resources to meet user demand since they share resources across numerous users. Full node wallets, on the other hand, may be unaffected. Transactions may be somewhat delayed, but each wallet will have the dedicated resources, including its own network connections, to attempt the submission. dApp providers should follow similar principles: if particular network endpoints are offered, system resources should be adjusted to match demand.

## Chain v transaction confirmation

*‘What is Cardano’s TPS (transactions per second)?’* is one of the most common questions on Crypto Twitter. How many network confirmations does Cardano require before a transaction goes through? The solutions to these concerns necessitate a more in-depth examination of the principles of chain confirmation and transaction confirmation, as well as their relationship to the protocol.

**Chain confirmation**

This is the threshold at which the protocol guarantees that the chain will not change any further due to randomness or random occurrences. After enough future k blocks have been issued, chain confirmation happens at some point in the future. The stability window is the period between now and when chain confirmation for a certain transaction happens (that is, the number of slots required for a block to become stable, where stability is defined as a block that cannot be rolled back). The formula for calculating this window is:

            3k/f 

- where k is the parameter that restricts a pool’s growth by lowering its rewards yield beyond a particular threshold, 
- f is the parameter that determines a pool’s maximum size 

**Transaction confirmation**

When a transaction is accepted into the chain, it becomes immutable at this point. The terms ‘block depth’ and ‘settlement window’ are used here. If the block containing the transaction is deep enough in the chain, it is deemed confirmed. Deep enough is a relative term: the depth of a block shows how many further blocks have been added to the chain since that block was introduced. Because blocks have depth, the transactions included within them have depth as well.

The transaction is deemed verified when the depth of a specific block exceeds a certain threshold, and the assets in that transaction can be used ‘safely’ (i.e., the protocol can guarantee the transaction is immutable, so the assets can be traded, exchanged, etc).

The settlement window is the amount of time between when a transaction is confirmed and when the transaction’s assets may be utilized to swap with other assets. A transaction becomes immutable as soon as its depth is greater than 3k/f slots (that is, 129600 slots on current mainnet, or 36 hours). 

**The chance of immutability**

Another factor to examine when deciding whether or not a transaction is verified is its possibility of immutability. The likelihood of a transaction being immutable is proportional to the number of blocks added to the chain since the transaction was approved. The bigger the number of blocks added, the more likely the transaction will become immutable. When a transaction’s depth exceeds 3k/f slots, it becomes immutable. The Ouroboros Praos protocol guarantees this.

Sebastien Guillemot covers transaction finality, amongst other in things, in this informative deep dive on *Cardano & Algorand: Leader Selection Explained*

## P2P (peer-to-peer)


**_To be uploaded soon..._**


[^1]: A server is a computer program or device that provides a service to another computer program and its user, also known as the client.
[^2]: **BitTorrent** is a communication protocol for peer-to-peer (P2P) file sharing which is used to distribute data and electronic files over the Internet. BitTorrent is one of the most common protocols for transferring large files, such as digital files containing movies or music.
[^3]:  Comparing 4 decentralized data storage offerings, techtarget.com/searchstorage/tip/Comparing-4-decentralized-data-storage-offerings
[^4]: A **gossip protocol** is a procedure or process of computer peer-to-peer communication that is based on the way epidemics spread. Some distributed systems use peer-to-peer gossip to ensure that data is routed to all members of an ad-hoc network. Some ad-hoc networks have no central registry and the only way to spread common data is to rely on each member to pass it along to their neighbors.
[^5]: 6 types of blockchain consensus mechanisms, essentialcardano.io/article/6-types-of-blockchain-consensus-mechanisms
[^6]: Fernando Sanchez, ‘Why They’re Calling Cardano the Green Blockchain’, iohk.io/en/blog/posts/2021/08/17/why-they-re-calling-cardano-the-green-blockchain/
[^7]: About stake pools, docs.cardano.org/getting-started/operating-a-stake-pool/about-stake-pools
[^8]: Lark Davis interview, youtu.be/BptZkkNN3tw?t=575
[^9]: Mempool role in multiple transactions, docs.cardano.org/core-concepts/multiple-transactions
[^10]: Kiayias, Russell (2018) 'Ouroboros-BFT: A Simple Byzantine Fault Tolerant Consensus Protocol', eprint.iacr.org/2018/1049.pdf
[^11]: David, Gazi, Kiayias, Russell (2017) 'Ouroboros Praos: An adaptively-secure, semi-synchronous proof-of-stake blockchain', eprint.iacr.org/2017/573.pdf
[^12]: Badertscher, Gazi, Kiayias, Russell, Zikas (2019), 'Ouroboros Genesis: Composable Proof-of-Stake Blockchains with Dynamic Availability', eprint.iacr.org/2018/378.pdf
[^13]: The framework of **universal composability** is a general-purpose model for the analysis of cryptographic protocols. It guarantees very strong security properties. Protocols remain secure even if arbitrarily composed with other instances of the same or other protocols. Security is defined in the sense of protocol emulation. Intuitively, a protocol is said to emulate another one, if no environment (observer) can distinguish the executions. Literally, the protocol may simulate the other protocol (without having access to the code). The notion of security is derived by implication.
[^14]:
[^15]:
[^16]:
[^17]:
[^18]:
[^19]:
[^20]:
[^21]:
[^22]:
[^23]:
[^24]:
[^25]:
[^26]:
[^27]:
[^28]:
[^29]:
[^30]:
[^31]:
[^32]:
[^33]:
[^34]:
[^35]:
[^36]:
[^37]:
[^38]:
[^39]:
[^40]:
[^41]:
[^42]:
[^43]:
[^44]:
[^45]:
[^46]:
[^47]:
[^48]:
[^49]:
[^50]:
[^51]:
[^52]:
[^53]:
[^54]:
[^55]:
[^56]:
[^57]:
[^58]:
[^59]:
[^60]:
[^61]:
[^62]:
[^63]:
[^64]:
[^65]:
[^66]:
[^67]:
[^68]:
[^69]:
[^70]:
[^71]:
[^72]:
[^73]:
[^74]:
[^75]:
[^76]:
[^77]:
[^78]:
[^79]:
[^80]:
[^81]:
[^82]:
[^83]:
[^84]:
[^85]:
[^86]:
[^87]:
[^88]:
[^89]:
[^90]:
[^91]:
[^92]:
[^93]:
[^94]:
[^95]:
[^96]:
[^97]:
