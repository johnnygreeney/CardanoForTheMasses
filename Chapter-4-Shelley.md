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


**_To be uploaded soon..._**


[^1]: A server is a computer program or device that provides a service to another computer program and its user, also known as the client.
[^2]: **BitTorrent** is a communication protocol for peer-to-peer (P2P) file sharing which is used to distribute data and electronic files over the Internet. BitTorrent is one of the most common protocols for transferring large files, such as digital files containing movies or music.
[^3]:  Comparing 4 decentralized data storage offerings, techtarget.com/searchstorage/tip/Comparing-4-decentralized-data-storage-offerings
[^4]: A **gossip protocol** is a procedure or process of computer peer-to-peer communication that is based on the way epidemics spread. Some distributed systems use peer-to-peer gossip to ensure that data is routed to all members of an ad-hoc network. Some ad-hoc networks have no central registry and the only way to spread common data is to rely on each member to pass it along to their neighbors.
[^5]: 6 types of blockchain consensus mechanisms, essentialcardano.io/article/6-types-of-blockchain-consensus-mechanisms
[^6]:
[^7]:
[^8]:
[^9]:
[^10]:
[^11]:
[^12]:
[^13]:
[^14]:
[^15]:
[^16]:
[^17]:
[^18]:
[^19]:
[^20]:


[^89]:
[^90]:
[^91]:
[^92]:
[^93]:
[^94]:
[^95]:
[^96]:
[^97]:
