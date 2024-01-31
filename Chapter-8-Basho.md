# Chapter 8: Basho

*‘The journey itself is my home’* ― Matsuo Basho

There are two eras left on the Cardano roadmap, and we’ll see over the next two chapters just how interconnected they are. They are being worked on in parallel.

## Scalability Defined

Cardano’s roadmap initially focused on establishing a decentralized, secure network. The innovative proof-of-stake model needed time to bed down and mature. There are now over 3,000+ stake pools confirming transactions, agreeing on the network state. This brings with it challenges in scaling a distributed system with no central, trusted nodes. The system must reach consensus to transfer assets, record of state and cryptographic proofs globally with constraints like network speed, differing hardware setups, etc.

Scalability is a blockchain’s **ability to handle usage or adoption**. Measuring scalability is not simply measuring the TPS (transactions per second) in any random scenario. Scalability is more nuanced than that. 

*‘Yes, but can it do a million TPS?’* is a familiar refrain often used without any context on crypto twitter. TPS (transactions per second) is perhaps the crudest measure to use as a comparison out of all those available. Transactions occur in a variety of sizes and formats. While this is true for Cardano, it is much more important when comparing two systems that are so significantly different. More pertinent questions are… Can it handle demand today? Does it have a realistic roadmap to handle billions of users in future?

Scaling a blockchain means improving the blockchain design using the various techniques and features outlined in this chapter. Many of them are complementary and interdependent on each other. The overall goal is to increase throughput. Digging deeper, this means improving performance based on these metrics:

- Throughput: the quantity of data that a system can process in a given length of time. Measured in Bytes per second (kilobytes per sec, kB/s) 
- CPU seconds (milliseconds) ms/s per wall clock for **script execution time**, ie. how long was the CPU busy for. 
- Finality: the amount of time it takes for an action’s consequence to become immutable and true for everyone in the system
- Concurrency: the amount of work that various actors can do without interfering with one another.
- Size of transaction(s)

At time of writing, blocks on the Cardano mainnet are created approximately every 20 seconds, with a max block size of 90kB and max transaction size of 16kB. You can review all the latest parameter settings on cexplorer.[^01] 

Any blockchain can appear fast and sexy using tiny transaction sizes and no scripts. Some high profile blockchains have centralized characteristics such as a minority of validators controlling disproportionate amounts of stake. It’s easy for a blockchain to compromise on decentralization then boast astronomical TPS figures, but if it needs to be stopped and restarted regularly, it should be a clue that it’s not really what it seems.   

You can configure protocols to maximize throughput, but throughput means something different in a UTXO system than it does in an account-based system. TPS on Cardano is yet more nuanced due to its native asset standard. eUTXO allows hundreds, even thousands, of native assets to be transferred in a single transaction. A more accurate metric[^02] is TPT (transactions per transaction). eUTtxO.org is a blockchain explorer created by Peter Oravec. It is an excellent learning tool to understand and visualize how transactions work on Cardano. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig81.png "figure 8.1")
<br>**Figure 8.1:**  @oravecpeter tweets about eUTtxO.org *‘There are 923 outputs of these two transactions, each output can be different recipient so 923 TX... this is superpower of UTxO... everyone will use this because it's super cheap to do all this stuff in single TX...’* 

Unlike many blockchains who adopt a ‘move fast and break things’ approach, Cardano has always stuck to a deliberate, careful and methodical strategy. Despite this relative conservatism, Cardano was the most developed crypto project on GitHub in 2021,[^03] 2022[^04] and yet again in 2023.[^05]

IOG outlined their Basho strategy in a 2022 blog post[^06] and Charles Hoskinson gave an update in his July 2023 video *Basho, Input Endorsers, and the Future of Scalability.*[^07] 

Nearly everything on Cardano occurs as a transaction, and gnerally speaking resources are consumed from these types of activities…transferring ada, issuing assets, executing smart contracts, voting, adding metadata …and you can usually break it into three broad categories and so you have network, you have data, so what you're storing, and then you have computation.

There is no ‘magic bullet’ for scaling blockchains, it’s done by tweaking parameters and combining different solutions that generally fall into two categories:

- Layer 1 solutions: upgrades applied to the mainchain protocol, cardano-node, etc. 
- Layer 2 solutions: offloading workloads, extending functionality and integrating other blockchains with sidechains, ZK rollups and state channels like Hydra.

So far Cardano has scaled to meet demand, given its ambitious goal and numerous constraints. Changes made for the Vasil hard fork have borne fruit however DeFi and RealFi will begin in earnest in the coming bull market cycle. There are several stablecoins launching, Oracles like Charli3 will mature, partner chains coming, over 1,300 projects are ready to join the existing ~ 150 projects. 
 
Scaling solutions are usually categorized as either **On-chain solutions** which encompass block size increases, pipelining, input endorsers, parameter adjustments, Plutus script enhancements, node enhancements and on-disk storage improvements. Then there are **Off-chain solutions** including sidechains, partner chains, Hydra, off-chain computing and Mithril. 

## Ongoing enhancements

As part of the Basho development phase, parameters need to be tweaked. A flexible infrastructure that can bend, but not break, is key as conditions change. Some considerations when making changes are:

- **Increased block size** enables more transactions to be fitted in a block. During times of network saturation, there will be reduced waiting time for transactions to be accepted by a block, which is a positive. There is, however, a cost. It takes longer for larger blocks to propagate throughout the network. Nodes will also need additional time to validate transactions as a result of this. Although increasing the block size might improve network speed, such adjustments should be done with care. It’s important to progressively alter settings and monitor the outcomes during high saturation times to guarantee that the increase does not impact block adoption time. 

- **Block level limit**: increasing the amount of memory units (abstract memory units) available to each script in the block. Scripts express various kinds of logic in order to spend UTXOs. 

- **Mempool size**: The size of the mempool is continually tweaked. When adding transactions to a block, the mempool acts as a network buffer and may cause a little delay. However, increasing the size of the mempool will not boost network throughput since transaction queues would remain the same. The mempool enables for a fair adoption of new transactions that arrive at random

- **Plutus requires resources**, both computational (CPU) units and memory units, in order to do useful things with a Plutus script. Plutus memory limitations can be extended, allowing for the creation of more complex Plutus scripts or allowing current scripts to handle more data items, enhance concurrency, and extend their capabilities. 

Timeliness consideration when increasing throughput:

- Timeliness: the time it takes to adopt a block. The entire ‘budget’ for block adoption is set at 5 seconds for a block to spread through 95% of the network, with Plutus scripts having a budget in the milliseconds. This is done to avoid monopolization by allowing the block to contain both scripts and simple transactions. 

- Throughput:  Users will experience longer block adoption times if the number of blocks is raised dramatically all at once. That’s because throughput and timeliness are at odds: boosting throughput means greater network performance, but it might come at the expense of delays when the system is overburdened.

**Congestion** is minimized by efficient systems. Cardano’s network utilizes **‘backpressure’** to control overall system stress. While certain individual users may report higher transaction wait times during a big NFT drop, this does not indicate that the network is ‘struggling.’ It really signifies that the network is working properly, in what’s known as graceful degradation.

Ouroboros (**Praos**) has precise criteria that must be fulfilled to achieve its **security objectives**, with block propagation time being a priority. Block propagation time refers to how long it takes for a newly minted block to be propagated through 95% of the staked ada nodes on the network. For Praos to remain secure, new blocks must be propagated every 5 seconds.

Most parameter updates have side effects. For example, increased block size would automatically lengthen the time it takes to propagate blocks; thus, any modifications must be monitored to ensure increased speed doesn’t jeopardize network security. This 5 second budget will be expanded in future Ouroboros iterations. 

**Node (cardano-node) enhancements**  

The node is central to everything in Cardano. It stores a full copy of the blockchain, processes ledger rule and plutus scripts, creates transactions and certificates, distributes (diffuses) transactions and blocks across the network. It calculates and distributes staking rewards to the delegators directly as well as to the stake pools. The node ensures decentralization as 3,000+ stake pool operators run the node. When you use your wallet, you are using the node. So, a lot is going on under the hood to make the chain work. It makes sense, then, to improve the node’s performance where possible.

Improvements allow for a more uniform distribution of stake and reward calculations over epochs, allowing for larger block sizes. Memory use is also more efficient overall. Memory compression minimizes RSS[^08] footprint, while memory sharing reduces the amount of data that needs to be instantiated. 

The Node team continues to attend workshops around the Voltaire upgrades outlined in CIP 1694 (the proposal on how Voltaire should be implemented). There will be gradual, iterative upgrades to the Node to accommodate the changes to the on-chain governance structure. The node will facilitate on-chain voting, including the guardrail mechanisms outlined in the constitution. The constitution itself will be recorded as a hash on-chain. Much of the detail for CIP 1694 was thrashed out in 2023, and 2024 will be all about implementing governance and the cardano-node will naturally be central to everything. More about Governance shortly.

As Node updates come thick and fast, it’s best to check the release notes[^09] for the very latest.

**Plutus V2 enhancements**   

At ScotFest in Edinburgh, Andrew Sutherland (Plutus Compiler Team Lead), reviewed the year since PlutusV1 was launched and subsequently enhanced with V2 in September 2022. Over the year his team ran, on average, half a million Plutus scripts per month on a nightly regression testing[^10] system. Such a focus on quality bore fruit with Plutus compiler optimizations and a 30% increase in script efficiency. The various enhancements made with the Vasil hard fork led to faster core interpreter, faster untyped Plutus Core execution and lower transaction fees. Sutherland credited the CIP process as the steering force behind the progress. 

MuesliSwap (muesliswap.com), the first native DEX on Cardano, took part in a benchmarking case study for Plutus V2 scripts. The results were a 90% reduction in transaction size and a 50% saving on transaction fees. 

The CIP 49 ‘SEC P’ Valentine hard fork in February 2023 opened up a new world of interoperability options. These are crucial building blocks for bridge security, among other use cases. 

As 2023 drew to a close, there were concerns expressed regarding Cardano’s ability to scale in the next bull market. SM₳UG[^11] observed '40% of Cardano blockchain, 60/150 GB are PlutusV1 scripts duplicated over & over again.arm’ because scripts can't be referenced in Plutus V1 and must be included again each time they're used. Pi Lanningham submitted a CIP[^12] proposing a backwards compatible way to support script references in Plutus V1 scripts. 

On the Cardano Forum, Pi also wrote up his reasons[^13] for tweaking parameters to prepare for increased DeFi activity. Meanwhile, Rick McCraken also posted a PCP (protocol change proposal) making a case for a block size increase.[^14]

You should be coming round to the notion that everything is related in Cardano. Many of the solutions discussed in this chapter require a hard fork to implement changes to the base protocol. Deciding on which parameters to change, when to execute updates, and by whom, can lead to robust discussions. Opposing views and priorities are inevitable as the ecosystem grows. Governance is being gradually transitioned from the genesis entities to the wider community. How do we debate key issues and decide a path forward is the subject of the next chapter. 

## Pipelining

Before Pipelining was introduced, a block was minted by an SPO, that’s a new block in the blockchain that had to be validated and sent onto a peer. The problem was that peers also had to validate it and then send it onto their peer and that’s how the blocks diffused across the network.

By combining validation with propagation, the time it takes for a block to propagate is reduced. By minimizing the ‘dead time’ between blocks, the objective is for blocks to be propagated to at least 95% of peers within 5 seconds (block propagation overhead). This allows flexibility to make other scaling adjustments, such as raising block size, or other Plutus parameter limits.

Pipelining is a natural progression of Cardano’s ‘plumbing’. It’s an important part of the scaling strategy, and a logical approach to ramping up Cardano’s capacity as the ecosystem expands. Each update is carefully monitored and reviewed for at least one epoch (5 days) before proceeding with subsequent changes. A decentralized network architecture must be scaled depending on real-world usage, notwithstanding the substantial research and technical effort that has gone into creating and installing the system.

**Diffusion pipelining**

Pipelining, or more specifically, diffusion pipelining, is a consensus layer innovation that allows for speedier block propagation. It allows for more headroom, allowing Cardano’s performance and competitiveness to improve even more. It’s important to understand the system behavior of how blocks propagate, to see how this strategy accomplishes its purpose.

As it passes around the chain, a block goes through 6 stages:

1. Block header[^15] transmission
2. Block header validation
3. Block body request and transmission
4. Block body validation and local chain extension
5. Block header transmission to downstream nodes
6. Block body transmission to downstream nodes

The path of a block is highly sequential. At each node, all steps occur in the same order every time. Block transmission takes a long time due to the large number of nodes and the ever-increasing quantity of blocks. Diffusion pipelining layers some of the above stages on top of one another, allowing them to happen simultaneously. This takes less time and boosts throughput.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig82.png "figure 8.2")
<br>**Figure 8.2:** Pipelining (courtesy of @jJosjuaThreatt tweet)

The time savings provided by this technique will allow Cardano to expand even further, including adjustments to:

- Block size – the larger the block, the more transactions, and scripts it can accommodate
- Plutus memory limitations - the maximum amount of memory that a Plutus script may use
- Plutus CPU limits - a script may be given extra computing resources to execute more effectively.

Pipelining makes sure that the block header referencing the hash of a previous block is propagated correctly. Metadata included in the next block contains the body of the previous block. This is a safeguard to prevent DDoS (distributed denial of service) attacks even without full block confirmation.

**From theory to practice**

Diffusion pipelining was created with the goal of achieving quicker block propagation while avoiding ‘destructive’ alterations to the chain. Because nodes depend on these current approaches, IOG did not want to eliminate any of the protocols, primitives, or interactions currently in use in Cardano. Instead of modifying how things operate now, they’re establishing a new mini protocol whose purpose is to pre-notify subscribing entities when a new desired block is detected, prior to full validation. Implementing Pipelining didn’t require a hard fork and can be rolled out with a standard node release. It was introduced without fanfare the same time as the Vasil hard fork.

The ability to pre-notify peers and provide them a block before it is verified, allowing the downstream peer to pre-fetch the new block body, is the most significant feature brought by pipelining. This saves a lot of time since the time it takes to verify a block over several hops is reduced significantly. The network was stress tested post-Vasil and the initial results were very positive. The node is now running faster, with more throughput. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig83.png "figure 8.3")
<br>**Figure 8.3:** Tweet from Rick McCracken post-Vasil… *‘We are hitting the chain as absolutely hard as possible from DripDropz.... The graph shows the mempool in red on the phyrhose way above the Cardano chain capacity and the chain is running perfectly fine.’*

## On-disk storage

The Cardano node needs RAM[^16] when it’s running. It’s prudent to start moving things out of RAM, out of that expensive volatile memory into on-disk storage. This is a common practice in computer science. On-disk storage will improve the user experience for developers on Cardano.

By storing elements of the protocol state on disk, nodes will use less memory, allowing RAM-starved systems to operate nodes as long as they have enough storage, and memory will no longer be a scaling restriction. The blockchain state will be able to increase significantly as a result of this.

There is a ‘UtxO HD’ project ongoing to move Cardano’s ledger state from being completely in-memory to being stored more on-disk. This is required to be able to scale to larger ledger states. It will also naturally ease RAM requirements for nodes. This feature will enable other roadmap items, such as parts of Ouroboros *Leios*. 

There is a living document[^17] on GitHub which goes into more technical details.

## Off-chain computing  
Offloading part of the computing, such as via Asynchronous Contract Execution[^18] (ACE), may improve the efficiency of the core network. Transactions take place outside of the blockchain, yet a trust model allows for quick and inexpensive transactions. This concept is still in research mode and will likely be implemented in a future update.

## Mithril

Mithril allows users to get the current state of a blockchain without recovering its entire history. Light, fast, efficient, and secure …Mithril is named after the fictional metal found in J. R. R. Tolkien's Middle-earth writings. It is lightweight but *'wrought of pure silver to the power and strength of triple steel'.*

At the Cardano Summit 2021,[^19] IOG researchers Pyrros Chaidos and Roman Oliynykov presented Mithril – a new protocol and network based on the research paper[^20] by Chaidos and Prof Aggelos Kiayias. Mithril utilizes a stake-based threshold multi-signature (STM) scheme to solve chain synchronization, state bootstrapping, and trust issues in dApps. Mithril has evolved into an open-source project with an aggressive biweekly release cadence. The release process[^21] is constantly refined for a smooth developer experience.

The original paper, and related blog[^22] by Olga Hryniuk, are quite technical and outline the long-term vision for the protocol. Like all agile, open-source projects, the final implementation might vary. What is clear is the burning need for a solution like this to enable faster syncing to the blockchain.

Piggybacking on the security of Cardano’s staking system, Mithril enables stakeholders to vouch for some fact, with a weighting proportional to their stake. Mithril’s initial proof of concept is to bootstrap a full Cardano node, however, it is flexible to apply to other protocols. For example, its main feature of validating the state snapshot can be applied to data exchange between sidechains, roll-ups, on-chain voting... Any many-to-one scenario is a potential use case. 

Mithril is an overlay sitting on top of Cardano’s Layer 1 mainchain, allowing users to create proof certificates. The certificates produced by Mithril have the same security properties that Ouroboros has. This has profound benefits. For example, millions of votes could take place off-chain, and then be aggregated together as a threshold signature. It would ultimately only be a single transaction on-chain. A full node like Daedalus can sync much quicker and a light wallet now has full node security, even though it’s a light client.

**How it works**

The STM (stake-based threshold multi-signature) scheme described in the original research paper is now available as a stand-alone core library on GitHub. It contains the full set of primitives of the Mithril protocol and is stand-alone in that it’s blockchain agnostic, it can potentially run on any PoS blockchain. 

- **The Mithril Network** sits on top of the Mithril Core library. There are three node types in the current proof of concept setup. 
- **The Mithril Signer** is run by a (SPO) stake pool operator, side by side with the Cardano node. It signs the ledger state, ie. creates individual signatures.
- **The Mithril Aggregator** collects the Signers’ signatures and creates multi-signatures, then embeds them in certificates. The aggregator also creates and stores the ledger state snapshot archive. These can be large, in the tens of GBs, and will grow as a blockchain grows.
- **The Mithril Client** restores (bootstraps) a full Cardano node by taking a snapshot and its certificate chain from the Aggregator node and verifying their validity with Mithril cryptographic primitives.

The Mithril architecture diagram is not for the faint hearted and difficult to capture the scale in a book. If you want to dig deeper, go to Mike Hornan’s simplified graphic[^23] on the Cardano Forum. The Lottery analogy is often used to explain Mithril:

IOG Architect Arnaud Bailly speaking on Cardano360 May 2022[^24]

>One analogy that you can use to think about it is the lottery. So depending on the amount of stake, you draw tickets from a lottery, and depending on the amount of stakes you draw, depending on the amount of tickets you bought, your chances of having a winning ticket are higher. And so this is the same for Mithril ...you can potentially have several winning tickets. Once enough winning tickets have been drawn, over all the stake pool owners, then a certificate can be issued which provides a certified signature of the current state of the chain from a share, some share of the stake pool owners, from some predefined share... and this is what we call a snapshot.
>
>Now the snapshot is made available to clients, and the clients can verify it, they can verify these snapshots by checking the aggregate signatures from all the lottery winners, so to speak, and so from all the signers....and check that they are actually legit and this check also rests on checking that the stake distribution is legit, and this is done through checking the chain certificate down to some general certificate ...and once they have verified the validity of certificate, now they can just download the snapshot itself, bootstrap the node, without having to go through the hassle of verifying everything.

**Progress to date**

The Mithril Network was tested as a centralized version initially (IOG-operated Mithril Aggregator). This paved the way for a decentralized version on the Cardano testnet where SPOs run the Mithril Aggregators. At ScotFest,[^25] Jean-Philippe Raynaud’s demo showed how a Daedalus wallet synched 15 times faster with Mithril, compared to classical bootstrapping. Mithril is crucial for trustless light wallets as they would otherwise need a third party to sync blockchain history. Mithril will enable fast sync times but also benefit from the mainchain’s security properties. On-chain voting during the Age of Voltaire is dependent on Mithril also.

In early 2023, the Mithril team published an SPO on-boarding guide[^26] in preparation for mainnet release, which took place in July 2023. Later in October, the Mithril 2 research paper[^27] was published in partnership with Algorand researchers from Boston University. Mithril 2 uses ‘Approximate Lower Bound Arguments’ (ALBAs)  to prove knowledge of a large dataset without revealing the full dataset.

Romain Pellerin, IOG’s Chief Technical Officer, explained ALBAs have many use cases such as demonstrating possession of multiple digital signatures from different individuals, without revealing each signature. Charles Hoskinson was effusive in his praise for the paper:

> Mithril 2 is out. I’m very proud of this paper. It’s damn fine work.[^28] 

>‘Mythril 2 just came out… the ALBA construction really is as good as it gets, these compact certificates inside Mithril …so we're now at a point where I think it's prudent to start talking about integrating Mithril itself into the Cardano blockchain ledger itself…’[^29]

He revealed in the closing keynote of the Dubai Summit[^30] that Mithril can now bootstrap Daedalus in the lab in 20 minutes, where it used to take 3 days. 

Zooming out, Mithril’s roadmap is based around these key milestones:

- Mithril beta: mainnet launch with volunteer SPOs
- Mithril MVP (2023): an incentivized protocol with additional features to support basic use cases, such as fast bootstrapping and secure light wallets.
- Mithril (2024): a fully decentralized and self-sustaining Mithril ecosystem.

To follow the latest Mithril news, read the weekly development updates on Essential Cardano[^31] every Friday, follow mithril.network and contribute to the Mithril repository on GitHub[^32]

## Hydra

Hydra introduces isomorphic[^33] state channels to increase throughput, decrease latency, save money with reduced transaction fees and storage needs. IOG developed Hydra as a solution for Cardano and related networks using a principled, evidence-based methodology. Hydra is the result of substantial research and a critical step toward allowing decentralized networks to grow securely to meet global demands. Hydra makes it easier to perform transactions off-chain while still utilizing the main-chain ledger for secure settlement. 

Hydra can sound very complicated and is sometimes confused with similar solutions. Let’s begin by clarifying what ‘isomorphic state channels’ are. ‘Iso’ is a prefix meaning equal, for example, isometric means equal measurements. ‘Morphic’ means relating to shape or form. So isomorphic means having the same structure and properties. 

‘State channels’ extend the notion of payment channels to also support smart-contracts over off-chain channels. Participants in the channel can now, in addition to traditional transactional payments, execute scripts to handle complex logic, off-chain, before committing the result back to the layer 1 later.

Participants lock funds into a smart contract. They can then transact with others in the state channel, off-chain, in whatever fashion meets their use case. Afterwards, the outcome is settled on-chain, without requiring the full transaction history of what occurred off-chain in the meantime. 

Developers can leverage Cardano’s proven infrastructure to develop wallets and dApps that communicate with the layer 2 system, drastically reducing the learning curve for Hydra. A Hydra Head may also be formed without the need for any initial funds from the receiving party, ensuring a seamless user experience.

**Hydra protocols**

Hydra is a distributed ledger scaling solution that meets all three of the aforementioned scalability challenges: high transaction throughput, low latency, and minimum storage per node. While Hydra is being developed in collaboration with the Ouroboros protocol and the Cardano ledger, it may also be used with other systems that have the same properties as Cardano.

Hydra’s overall aim is to provide a cutting-edge layer 2 scaling solution for Cardano. Hydra will save expenses while boosting throughput and ensuring security. Hydra replicates the main chain’s functionality while minimizing friction for users, but still allows the flexibility of having a different fee structure and timing constraints on the layer 2. 

Hydra is a system made up of many subprotocols that work together to solve a single problem: scalability. Cardano’s ecosystem is diverse, with numerous organizations with varied technological capabilities: the system needs to support stake pools, light wallets, DEXs, and other end-users with a variety of computing performance and availability characteristics. It’s unreasonable to expect a single-protocol, one-size-fits-all method to provide overall scalability for such a diverse group of network actors.

In an early blog,[^34] the Hydra architecture was broken down into four components: the head protocol, the tail protocol, the cross-head-and-tail communication protocol, as well as a set of supporting protocols for routing, reconfiguration, and virtualization. Although it was originally developed as part of the Ouroboros research agenda, it has taken its own route and is now an agile open-source project with a release cadence of weeks. 

**Hydra Head**

The Hydra ‘head’ protocol was the first part of the Hydra architecture to be released. The Head protocol began to take shape in 2020, especially during this early implementation and proof of concept[^35] stage. IOG’s understanding has evolved since then, and 2022 saw the formalization and implementation of a variation on the ‘Head’ protocol in the original paper. 

Hydra acts as dApp-embedded software for developers seeking scalability. It is implemented in two parts:

- On-chain scripts that execute the Hydra Head protocol
- Hydra node, a software stack which provides a high-level interface using standard web technologies like WebSocket and JSON.

To operate a Hydra Head, a working Cardano node is a prerequisite. You then run a Hydra node, connected to other Hydra nodes and a Cardano node. Each Hydra Head can consist of several Hydra nodes. The Hydra team state in the docs that their current goal is anything up to 100 nodes per head. On-chain code will be the same between Cardano and a hydra head. This is one of the major selling points of the hydra design. 

The potential Hydra Head topologies and use cases are listed in detail on the aptly named website https://hydra.family. The community is actively encouraged to give feedback on the roadmap.[^36] 

**Hydra Head ‘Poker game’ analogy** 

The Hydra Head protocol is best used where participants, well-known to each other, agree to form a network but don't trust each other with the funds. A Hydra Head enables them to do so with ways to secure their assets, backed by the ability to settle disputes on the layer 1.

There are several use cases explained on the Hydra site, but the poker game is perhaps the most intuitive analogy to explain Hydra Heads. Consider Heads as a ‘private poker table’ where players bring their own chips to play with. The game may be played for as long as the participants like. If no one participates, the game will not advance. Participants are, however, able to leave with their chips. The game will terminate with the existing pot distributed if they do so.

A channel is a communication link between two or more peers. To be a part of a Head, you must be one of the peers. Channels establish isolated networks that may develop independently of the main network. Participants on these alternate networks use a different, simpler consensus algorithm: everyone must agree on all transactions that pass through. As a participant, I am unable to lose money that I have not specifically decided to lose. Why? Because every binding transaction needs my express permission.

Participants may make financial commitments to a Head while creating it. This entails transferring funds off-chain to a script address that binds them to a set of rules. The script ensures that the protocol is executed safely on-chain, and that participants cannot defraud one another. Any participant, however, may choose to leave the Head at any moment by closing it. In this situation, everyone gets the most recent state they consented to off-chain, on their parallel network.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig84.png "figure 8.4")
<br>**Figure 8.4:** Courtesy of Cardanians’s medium post ‘Hydra: Cardano Scalability Solution’[^37] 

The on-chain script’s dealer at the table guarantees that everyone follows the rules and doesn’t cheat. In conclusion, there are the same number of chips out as there were before the game began, although they may have been rearranged throughout the game. While the ultimate outcome is known outside of the table, the players are the only ones who know the history of all bets taken throughout the game. The funds, or existing table pot, are unlocked based on the most recent agreed upon snapshot.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig85.png "figure 8.5")
<br>**Figure 8.5:** Hydra Head use cases, from ScotFest talk by Hydra Product Manager, Nebojša Vojvodić 

**Evaluating the Hydra head protocol** 

Hydra Heads are known for their ability to achieve near-instant finality inside a Head. Setting up and closing a Head might take a few blocks. Simulations have shown that a single Hydra head can reach up to 1,000 TPS (Transactions per second), so if 1,000 heads are run in parallel, it should be possible, in theory, to achieve a million TPS. 

So, is Hydra able to call whatever TPS number it wants? In principle, the answer is yes, which highlights a flaw in the common[^38]  use of TPS as a system comparison measure. While it’s easy to simplify the complexity of evaluating protocol performance to a single number, a lofty TPS claim is almost worthless without further context. With this in mind IOG adopt the following practices:

- explicitly describe all of the variables that affect the simulation: transaction size, time to verify a single transaction, time required for cryptographic procedures, allotted bandwidth per node, cluster size and geographical distribution, and transaction parallelism limitations.

- evaluate the protocol’s performance on baselines that define the underlying network and hardware infrastructure’s exact and absolute bounds. How effectively one approaches such boundaries indicates how much space for progress there is. 

The research paper[^39] (Section 7: Simulations) has further information and graphics. The Hydra team regularly post testing results on the site[^40] and welcome more real-world test scenarios. Hydra started bearing fruits in 2022. Obsidian Systems and IOG announced *Hydra for Payments*[^41] which is an exciting prospect for micropayments on Cardano. At the *Rare Bloom* event in Denver, SundaeSwap demoed how their protocol could work as a Hydra Head.[^42] 

Hydra’s team lead, Sebastian Nagel, presented at the 2022 Cardano Summit in Lausanne.[^43] The goal was now for Hydra to be the number one dApp on Cardano, regardless of how this is measured. 

Hydra Head is only the first part of a larger group of protocols as described in Chakravarty and co *Hydra: Fast Isomorphic State-Channels*. As Hydra matures and adoption grows, several topologies will be implemented. It’s best to check hydra.network for the latest roadmap. Current plans include a ‘Delegated Node’, a ‘Managed Hydra Head’ (aka Hydra as a Service) and a ‘Star-shaped Network’. 

Sep 21, 2022. Re: Hydra: CH[^44]

>When you look at things like Mithril, Hydra… these are extensions of known concepts, like Mithril is a threshold signature idea, and they construct these proof certificates, and then when you do transactions, they're paired with proof certificates, and it gives you the inclusive accountability …it's not a new idea, it's like 10 years of talking about this stuff. We just implemented it. It's a lot of hard cryptography to implement, but once it's done it's done, and it's more about how do you distribute the certificate and build them?
>
>Hydra is everything Lightning[^45] wanted to be when it grows up. The problem with Lightning is that it's not a hard protocol… payment channels and state channels. The hard part is the fact that Bitcoin is not programmable. So, 95% of your effort is trying to figure out how do you get a model, that's not designed for this, to work with this.
>
>It's almost like when they were upgrading the Hubble telescope in space, you know, after you've launched the telescope into space, it's not upgradable anymore, but yet NASA is like ‘well we need to fix it’. So, they sent astronauts out there, and they put this giant contact lens on it, and they had to figure out how to open shit that you really can only open on Earth, in space. So, you have this guy like basically wearing an oven mitt, with a very tiny screwdriver floating in space, trying to unscrew a panel and gradually upgrade old circuitry, and make it better without getting himself killed. So that's Bitcoin in a nutshell, when you try to apply Lightning.
>
> Well with Cardano, we're on Earth, okay, it's programmable meaning that we can always go and pull a module out, put a new module in, and do these things. So, with extended UTXO and Plutus, there's enough there that you can build rich isomorphic state channels. So basically, you can take state and assets, and you can batch and bundle them together, and put them into a layer 2 solution…and then you can use it for microtransactions, you can use it for smart contracts, but then you can build modules on top of it to do specific applications like DEXs, voting… these types of things. In particular, one area I'm very interested to use Hydra in 2023, is to reuse that technology to do all the stuff we're doing right now with Catalyst and voting.

**Oct 3, 2022. Re: Hydra, Let’s Talk Basho.** CH[^46]

>So the way that we designed Plutus is that you have an on-chain component, and that's your Plutus script… and then you have this idea of off-chain infrastructure that coordinates with the dApp to run things… and this is very common in the Ethereum model as well and they have all these things to combine these two, and then off-chain infrastructure sometimes is centralized, sometimes it's not centralized, it depends on the specific dApp. The idea of Hydra is that it would be part of that off-chain kit, so it would be embedded in dApps that require a lot of scale, and basically it would do something similar to what's occurring with Mithril, where you go many-to-one or some

Matthias Benkort’s retrospective blog post[^47] noted ‘one might say 2022 was about ramping up software quality and preparing Hydra for the first pioneers to build.’ In January 2023, IOG collaborated with Mlabs (mlabs.city) to produce the *Implementing auction projects using Hydra*[^48] paper. The study explores various ways to implement digital asset auctions using the Hydra Head protocol. This is central to how DEXs and NFTs will function on Cardano. The paper addresses current project needs and considerations in detail. Discussions are ongoing on Discord and GitHub. 

The Hydra team explored integration with the wider ecosystem in 2023, for example, Hydra support for Kupo.[^49] They improved documentation with a Hydra node architecture explainer.[^50] They also updated the Hydra tutorial[^51] to simplify the getting started experience while also including Mithril to fast bootstrap the cardano-node. They worked closely with the Aiken team, exploring the idea of moving the Plutus validator scripts to Aiken. Elsewhere, TxPipe now offer a *Hydra Head as a service* through their platform Demeter (demeter.run).

Notable milestones included the release of the first mainnet-compatible Hydra node version.[^52]

The Hydra project is a joint effort by engineers at IOG, but also the Cardano Foundation and a growing list of contributors. The Cardano Foundation deployed *Hydra tally*[^53] to mainnet so more community members could attest and verify validity of Catalyst Fund results. Previously, only IOG could tally votes. The experiment explores how Hydra could potentially decentralize the process.

As the work of the Hydra and Mithril teams converged more and more, Sasha Bogicevic (Hydra) and Franco Testagrossa (Mithril) delivered a masterclass at the Dubai Cardano Summit where they showed how the projects can work together. The Mithril and Hydra also held a joint monthly review meeting,[^54] to talk about progress and related scaling projects. 

Follow the latest progress on the Hydra Head roadmap[^55]

**Hydra clarifications**

- There has been some discussion promoting Hydra as the ‘ultimate’ be-all and end-all Cardano scalability strategy. Hydra Heads provide a solid basis on which to develop Cardano’s scalability layer. They are a critical building piece that allows more complicated solutions to be built on top of the Extended Unspent Transaction Output (eUTXO) architecture. They are an important part of the scaling journey, but they are not the end goal.
Mithril’s development is closely tied to that of Hydra, with overlapping teams. Some of Mithril’s components can connect and work fine with Hydra. Their websites, mithril.network and hydra.family, share a similar format with excellent quick start guides, glossary, etc. As they are both open-source projects, anyone can contribute to these pages on GitHub.

- A Hydra Head is usually a relatively small-scale network created by a small number of people. Because these groups will be autonomous at first, looking at the total of their separate metrics is deceptive. Although Hydra Head protocol’s initial iteration will enable small groups of participants to scale up their traffic at a reasonable cost, it will not provide a solution for worldwide consumer-to-consumer (micro) payments or NFT sales right away.
Why not? Because the consensus inside a Head necessitates each participant’s response to each transaction, everyone needs to agree on each transaction. While this offers security assurances to participants in a Hydra Head, it limits the total number of participants in practice. IOG, and the growing number of contributors to the project, continue to research ways to expand the Hydra Head protocol’s capabilities. In 2021, there was a paper released from Tokyo Institute of Technology titled *Interhead Hydra: Two Heads are Better than One*.[^56] It is an iteration on top of Hydra Head proposing a mechanism for linking two Hydra Heads together, allowing the formation of a network of linked Hydra Heads in the long term. 

- There is a **risk for non-participants** as your funds are in the hands of the participants operating the Hydra Head. 

- A Hydra Head protocol is **not a sidechain**. There are no blocks created in a Hydra Head, nor is there any transaction history available outside the Head. New participants cannot join an existing Head. They need to be there from the start as an operating Head is an isolated, private channel.

## Sidechains 

A sidechain is a blockchain that is linked to a main blockchain (the mainchain, or parent chain) through a two-way mechanism (a ‘bridge’) that allows tokens and other digital assets from one chain to be utilized in another and the results to be shared back and forth. Multiple interoperable sidechains may be joined to a single parent chain, each of which can function in a different fashion. 

A sidechain is the exact same concept as a blockchain. The difference is philosophical, not technical. The sidechain usually aligns with the mainchain, but a sidechain can have its own business logic, cryptocurrency, monetary policy, consensus rules, programming language, application domain, subset of users, smart-contract capabilities, stablecoins, use cases like NFTs, loyalty points, etc. Side chains are the same technically as a standalone blockchain, in that blocks are produced by validators. 

Unlike state-channels such as Hydra, they offer data-availability and participation for new users. In a state-channel, typically only participants of the channel can see what is going on in the channel, and they must be decided up front. Joining a sidechain is typically done by burning or locking assets on the mainchain, in return for an equal amount on the sidechain.

Cardano’s eUTXO model means the state is pre-sharded on the mainchain, so it’s easier to move state to a sidechain. Sidechains are ideal for medium to low-risk protocols. They are ideal for new, or growing ecosystems because the sidechain can avail of an established mainchain’s security, liquidity, wallets, and user participation. Sidechains lighten the load off layer 1 mainnet, all the while enjoying the veracity that’s provided by its parent chain. 

While there will be large transaction volumes running in parallel on sidechains, these transactions don’t reconcile on the mainchain so resources on the Layer 1 mainchain aren’t consumed by sidechains. 

IOG have been thinking about sidechains for quite some time, as far back as 2014, they reviewed Blockstream’s pegged sidechains paper.[^57] Then the was ScoreX,[^58] a flexible, modular blockchain framework that was built to enable blockchain experiments. It was an early IOG project before it was incubated at HyperLedger Labs.[^59] Ergo was just one example of a blockchain built using ScoreX. IOG has held regular talks with engineers at Hyperledger Fabric, an open source blockchain framework similar to ScoreX. They monitored the rise in popularity of Cosmos, a blockchain focussed on interoperability.

The sidechain strategy has been laid out as early as 2016, in the *Why cardano?* paper. The original proposal was for a CSL (Cardano Settlement Layer) and a CCL (Cardano Computation Layer). This vision manifested itself slightly differently in the sidechains model, in that there would be multiple CCLs.

So you see, a lot of deep thought and academic rigor went into Cardano’s architecture. It’s evident in how rewards incentivize sidechain partnerships. Ada holders traditionally get staking rewards in ada. The same SPOs that power the mainchain, will also provide staking liquidity for sidechains. So now, if the SPO you delegate to is also part of the sidechain SPO subset, you get rewards in that sidechain’s native asset in addition to your usual ada rewards. 

**Re: Sidechains, Let’s Talk Basho**. CH: 

> It's basically like super-Hydra. Hydra is dApp-specific, sidechains are ecosystem-specific

There are often trade-offs to running a sidechain. Increased throughput can mean less security. Bridge security is challenging in practice and there have been many hacks in 2022.[^60] However, Cardano offers a very secure layer 1 mainchain. Funds in a bridge contract are well protected and assets are securely transferred between sidechains based on the formal definition outlined in IOG’s *2019 Proof-of-Stake Sidechains* paper.[^61] 

The research describes how a new ‘firewall’ security property protects a mainchain from its sidechains. Potential failures on the sidechain won’t impact the parent chain. Project Catalyst, for example, is run as a sidechain of Cardano. Even if its safety is compromised, no funds are lost on Cardano. The paper also outlines a blueprint describing merged staking, cross-chain certification, and multi-signature for proof-of-stake sidechains.

Based on this research, IOG developed the Cardano EVM (Ethereum Virtual Machine) sidechain, Mamba, following a deliberate and iterative approach. It was an open-source sidechain protocol with a client written in Scala. Mamba is compatible with Ethereum’s tools and libraries enabling developers to write Solidity smart contracts, dApps, and ERC20 tokens on Cardano. Ethereum smart contracts could run unchanged on Mamba, with much lower *gas* fees.

The consensus protocol used on Mamba is Ourorobos BFT. This was an earlier iteration of Ouroboros used on the Cardano mainnet. It is a simple, deterministic protocol for ledger consensus that tolerates Byzantine faults.[^62] There are different versions of proof-of-stake (PoS), which are suited to different use cases on sidechains and main chains. Sebastien Guillemot gives an excellent breakdown of the trade-offs in his video *Cardano & Algorand: Leader Selection Explained*. 

Dominik Zajkowski, IOG Technical Architect, expanded on this vision at ScotFest. He explained the Plutus scripts for maintaining the EVM Mamba sidechain would be made available as a toolkit[^63] to be used as a reference template, a kind of SDK for future sidechains with Cardano being the core root of trust. Zajkowski explained the toolkit was intentionally incomplete so as to invite the community feedback on features they wanted to see. The documentation[^64] includes the technical spec. 

## Milkomeda 

Not everyone is enamored with Cardano’s current architecture. CTO and co-found of dcSpark, Sebastien Guillemot, questioned[^65] Cardano’s monolithic structure and why it has deviated from the initial vision in ‘Why Cardano?’. Having worked on the protocol since the incentivized testnet days, his views should be taken seriously. Having said that, there are trade-offs in any blockchain decisions. 

Cardano is an open ecosystem and people are free to launch sidechains using different models. The first Cardano sidechain was launched by dcSpark. Milkomeda brings EVM compatibility and a bridge for developers to the Ethereum ecosystem. Milkomeda is a portmanteau, named after the *Milky Way* and *Andromeda* galaxies which are due to merge in a few billion years. Milkomeda also brings EVM compatibility to Algorand as well, merging multiple ecosystems. What is interesting is Milkomeda is currently implemented differently on both blockchains. It is a Cardano sidechain with a growing number of dApps,[^66] but a Layer 2 solution on Algorand. 

Guillemot explained the differences and reasoning at the Rare Bloom event.[^67] As discussed previously, a sidechain is a blockchain that aligns technically with a parent chain but differs philosophically on key features. Milkomeda C1, for example, is the Cardano sidechain where they chose to keep the same base asset (ada) but has faster block times (4 secs) with instant finality. It wasn’t possible to implement Milkomeda as a Layer 2 solution on Cardano at the time due to some technical obstacles, which will likely be resolved as features like Mithril mature.

With funding from Catalyst,[^68] dcSpark added wrapped smart contracts meaning EVM contracts could be called directly from any Cardano wallet, extending interoperability further. The UX is frictionless, with the end user oblivious to the fact that they’re using an EVM underneath. Wrapped smart contracts also enable wrapped Oracles to provide off-chain data. This feature integrates access to existing EVM-based Oracles to the Cardano mainnet.

Milkomeda A1 is a Layer 2 on Algorand. While a sidechain gives you greater flexibility but less security, a Layer 2 gives you full security with mathematical proofs, but less flexibility as you need to program everything in zero-knowledge (ZK) circuits.

What is a Layer 2 scaling solution?

There are generally 3 types of Layer 2 solutions.

- State Channels (like Hydra, or the Lightning Network on Bitcoin)
- ZK Rollups
- Optimistic Rollups  

Both ZK and optimistic rollups collect off-chain transactions into a batch, then submit them to the Layer 1 blockchain as one transaction.

A **Zero-knowledge (ZK) rollup** is built on top of the existing Layer 1 blockchain to make the transactions faster, cheaper, scalable, secure, and private by not disclosing everything while transacting with the verifier. The problem with many other Layer 2 solutions is that they are not secure enough. There is a trade-off where they focus more on scalability, which can leave them open to exploits. ZK rollups are so powerful as it’s much faster to prove you know the answer, rather than doing the computing to get the answer. 

**Optimistic rollups** are less secure than ZK Roll-Ups but offer greater flexibility because they don’t require everything to be encoded in a ZK circuit. In contrast to ZK rollups where you prove everything is correct, you are just proving dishonesty (with Fraud proofs) as required. As the name suggests, you optimistically presume transactions are valid, or using fraud proofs to prove false transactions within 7 days.

ZK rollups are more scalable as they consume less blockchain resources compared to Optimistic rollups. ZK rollups are difficult to implement today, mainly because they take time to compile and can slow down your dApp. This is improving every year, however, and it is hot research space. 

Ethereum has a huge focus on ZK roll-ups with many projects trying to dominate. @StakeWithPride[^69] pointed out some dubious design fundamentals and values coming out of the Ethereum community. In a video from a core developer, there is an admission that a serious hack is likely with ZK roll-ups on Ethereum. The proposed solution is to leverage Intel SGX trusted enclaves[^70] to ensure security, which doesn’t sound very decentralized.

On Cardano, there was already the unsuccessful Orbis ZK project funded by Catalyst.[^71] Dr Markulf Kohlweiss announced the ZK Lab at Edinburgh University and dcSpark have marked ZK research as a priority in 2023. 

**April 20, 2022, ‘4/20 Hangout with Charles’ Twitter space**,[^72]

**Re: L2 scaling solutions, ZK roll ups**… CH:

> Why do we care about this technology? Why is this useful to me as a consumer? Ok, let’s say you go to a bar, and you get carded. When you show your driver’s license to the bartender, you reveal more than just your age. You reveal your precise age. Oftentimes, the driver’s license has an address on it. If you’re an organ donor or not, a picture of you, your gender, you reveal some of them... I think they put Social Security numbers on the driver’s license, military ID, and even more, a passport. You get all this stuff that the bartender should not know.
>
> The bartender is looking for a threshold condition. Are you above or below the drinking age? That’s all they need, it’s a Boolean yes or no. Are you over 21?... at or over 21? So, what a zero-knowledge proof can do is, for an identity system with digital ID, you can prove to that bartender that you’re over at the age of 21, but reveal nothing else about you. No other metadata, and an abstraction you can do that for any challenge response protocol. Are you a US citizen or not? Is the money that I've received taxed or not? Are you fully compliant with laws in the state of Colorado? or not? Yes or no. These types of things. Are you eligible to see this information? Yes or no. You remove that judgment in that respect.
>
> Now the other application is, do you own this money or not? Zero knowledge proofs are perfect for this application, because basically you’re proving that the money exists and that you have the right to spend it, but you’re not revealing which money it is, and you’re not revealing who you are. So that’s why they’re used in privacy systems.

**Other interoperability solutions** 

There is a growing list of builders on Cardano. For example, Wanchain[^73] is a bi-directional decentralized, non-custodial cross-chain bridge linking Cardano to other tier 1 blockchains. As well as being a decentralized interoperability solution, Wanchain is layer 1 proof-of-stake (PoS) blockchain with an Ethereum-like ecosystem that supports industry-standard Ethereum tools, dApps, and protocols. It has certain similarities to Cardano. Wanchain employs the Galaxy Consensus PoS consensus method, which employs several cryptographic approaches, such as distributed secret sharing and threshold signatures, to enhance random number generation and block creation processes. Galaxy Consensus is a continuation of Cardano’s own Ouroboros protocol.

To understand more check out *Rollups on Cardano Discussion*.[^74] IOG have contributed to this space with their paper on Sonic: Zero Knowledge SNARKS.[^75]

## Midnight *in the Garden of Good and Evil*

At ScotFest (Nov 2022), Charles Hoskinson revealed his team had been working on another cryptocurrency for the past four years. It is called *Midnight* and will be a Cardano sidechain with a native token called *dust*. As mentioned before, the way sidechains work on Cardano is as a partnership. Midnight gains decentralization, security, infrastructure, liquidity and a thriving ecosystem from Cardano. In return, Midnight pays rent in the form of rewards to Cardano SPOs and delegators. 

IOG reviewed existing privacy solutions like Monero and Zcash and felt they could do better. Research on the privacy requirements for smart contracts has been ongoing for some time. *Kachina-Foundations of Private Smart Contracts*[^76] is a paper Charles Hoskinson ranks as ‘one of our most forward-thinking publications’.[^77]

IOGs brains thrust (the likes of zero knowledge expert Dr Markulf Kohlweiss) went to work and reviewed other solutions like Zexe[^78] and concluded that three ‘must have’ properties were absent in the blockchain space today. Abbreviated to ‘ACE’, they are: freedom of Association, freedom of Commerce and freedom of Expression. 

These basic human rights are not always present in some jurisdictions for various reasons. Midnight will offer confidentiality and privacy with the ability to freely associate with people and engage in legitimate commercial transactions. 

There is also the regulatory side. It is not illegal to seek confidentiality and privacy in most circumstances. As many people believe crypto is cloaked in secrecy and only used for nefarious activity, new dApps need to protect user rights and wishes, but also enable them to comply with regulatory requirements. dApps on Midnight enable users to protect their own data, to keep their data in their own systems. They don't have to share everything but can share assertions about their personal data based on things like KYC and AML, and the body on the other side of the transaction can trust that those assertions are correct. Selective disclosure is not the same as a ‘back door’, fake news[^79] and FUD has already been called out and corrected on this matter. 

Midnight goes beyond just privacy transactions and attempts to support true confidentiality with private smart contracts. To implement this concept, certain data must be private to the public, but still enable voluntary or involuntary disclosures. This can be applied in many use cases. With the 2024 US election looming, consider how decentralized anonymous voting could work on Midnight. Eliminating the risk of vote tampering, a Dapp could leverage zero-knowledge cryptography to enable voters to register and prove they are eligible without disclosing unnecessary personal information. A similar use case would be for sharing patients medical records. The implications are far-reaching and profound. 

How will this be achieved? The documentation is not public yet but will likely involve decentralized IDs (DIDs) being tightly integrated with Midnight, linking identities and privacy. Light wallets will provide easy access to innovative features like *dead man switches*[^80] for estate planning and multi-party computation[^81] features. Monero and Zcash are proven solutions for keeping your transactions and tokens private, but programmability is required too. The Kachina paper explores how to write private smart contracts, and IOG has been busy bringing the theory to life. 


![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig86.png "figure 8.6")
<br>**Figure 8.6:** Why *Midnight* stands out, from IOG’s Chief Strategy Officer Rob Adams talk at ScotFest

After many years of research and development, they created a virtual machine in Typescript. This is significant in terms of developer adoption. Typescript (~35%), a superset of JavaScript (65%), is one of the most popular programming languages in the world.[^82] For perspective, Haskell adoption languishes somewhere between (1-2%). IOG are taking a developer-first approach with Midnight, in contrast to Plutus, which arrived some years after Cardano launched. 

With regulation on the industry’s doorstep, Midnight looks like an astute strategic move by IOG. Regulators have a daunting task trying to legislate for a nascent industry with emerging technology sometimes not yet in production. Midnight offers a potential middle ground where core principles of crypto can be upheld, but also enable dApps meet compliance requirements in different locales. 

Just one example is when a large global enterprise needs to comply with GDPR requirements in Europe, but still have a different US version to comply with requirements in the Bank Secrecy Act. Most companies face large penalties if they fail to keep user data private. There are many other obvious use cases from making medical data accessible, to enabling underground newspapers in volatile societies to operate.

Charles Hoskinson mentioned in his 2022 New Year’s Eve twitter space[^83] sidechains will be rolled out based on the Japanese martial arts concept of *Shuhari* …you learn, you do, then you teach. IOG ‘learned’ with the Mamba proof of concept, now they will ‘do’ with Midnight and ‘teach’ with various toolkits, blogs and formal papers. Eran Barak was unveiled as Midnight CEO and Dr. Vanishree Rao as its head of applied cryptography. Throughout 2023, the Cardano community craved more details about this new, mysterious *Midnight*. 

A long-awaited strategy update was delivered at the Cardano Summit 2023. Despite a keynote with the trademark whiteboard, there was still some confusion about the details. Chinese whispers led to FUD suggesting IOG was abandoning Cardano for Midnight, and that Midnight didn’t need Cardano to succeed.

**Midnight Special**

As time was tight on stage in Dubai, Hoskinson promised a new whiteboard video to clarify any gray areas. The follow up *Midnight Special*[^84] was comprehensive. There had been talk for some time about renaming sidechains to something more descriptive. Partner Chains would be the new model for interoperability on Cardano as it suggests each Partner benefits from the relationship. 

The new model would mean there would still be separation of layers, but now the Cardano Settlement Layer (CSL) would be renamed as the Cardano Asset and Settlement Layer(CASL).[^85] Its purpose and functionality would remain largely the same, ie. act as a proven, robust settlement layer for partner chains. The Cardano Computation Layers (CCL) would now be known as Cardano Service Layers(CSL)[^86] mirroring the philosophy of microservices, or service oriented architecture.[^87] Partner Chains, like Midnight, would have the flexibility to build their own computation layers using modular frameworks and existing components while still leveraging the CASL. Each (CSL) service layer might have its own distinct logic with unique tokenomics, consensus protocol, etc, however they will have the same ‘common ancestor’ in the CASL. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig87.png "figure 8.7")
<br>**Figure 8.7**:  The new partner chains model, graphic credit: cexplorer[^88]

Hoskinson explained they had learnt a lot from ScoreX, Mamba, Cosmos and more recently Polkadot’s Parity Substrate[^89] stack when devising Midnight’s architecture. Substrate is a proven open-source framework tried and tested on 190 Polkdot Parachains.[^90] It describes itself as a ‘Blockchain Framework for a Multichain Future’. Hoskinson went on to explain Midnight would use Substrate as a starting point, and would develop their own custom ‘pallet’ components.[^91] 

>And it's an open source project at the end of the rainbow too. And what's nice is we got kind of a huge leapfrog with getting Parity Substrate as a starting point, but it's really important to understand it’s not stock Parity Substrate. There’s going to be a humongous amount of upgrades, modifications and additions.
>
>For example, the Cardano network stack is being ported over…it's written in Rust, and so it's not ‘stock Parity network’…we spent 10s of millions of dollars building the best network stack in the world for cryptocurrency. We would be bloody insane to throw that away for our partner team framework. Brand new consensus protocols are being developed, and then run in this setting with Minotaur, and there's a lot of magic there…so that's all new code and you know, different ways of doing pallets, so all kinds of stuff.
>
>So there's a big deviation from what Substrate brought to the table, but then there’s an acknowledgement that there was a lot of amazing engineering work that the Polkadot community did ...they have 190 parachains that they tested it on. So it makes absolutely no sense to throw all that work away…  It's just hybridizing that and keeping the best parts and blending them…and frankly that's what we should be doing, as an industry… is that everybody's doing good work, let's stop fighting each other, let's acknowledge it and the highest compliment is not a tweet saying you're doing good work… the highest compliment is taking the code and building on top of that code, that's what open source truly means at its core.

Borrowing ideas and benefiting from others research is nothing new in the blockchain space, despite the rivalries and tribalism. For example, Polkadot’s BABE protocol[^92] took inspiration from Ouroboros Praos. 

Adopting a multi chain strategy with Substrate and leveraging the findings from the *Minotaur*[^93] paper, Midnight will be able to leverage multiple consensus protocols. We are entering uncharted waters now as Cardano can potentially be the settlement layer for more chains. Security will be provided by Cardano’s SPOs as before, but now Minotaur will allow validators from other chains to contribute. The introduction of Babel fees[^94] (still in research) will smooth integration as chains can transact in their own native currency, while still allowing Cardano SPOs to be compensated in ada. Its thought stake pool operators might run a ‘super node’ similar existing concept with Hyperledger FireFly’s open source Supernode.[^95]

Eran Barak gave more detail, explaining[^96] Midnight will be a 4th generation blockchain as it enables data protection and a multi-resource consensus model. Advancements in zero knowledge technology will allow data and metadata to be protected. While the details will be revealed in time, he stated Midnight would feature a shielded Ledger for confidential information on chain, but also an unshielded Ledger for public data on chain. The user now has the capability of selective disclosure. 

The tokenomics are still to be disclosed but will be made up of a shielded token, dust, for private transactions as well as a second unshielded token for network liquidity and security. This dual token model will mean Enterprise users can have table stakes they expect for business like price predictability, ability to pay in Fiat, SLAs, etc. There will be Typescript templates for zero knowledge circuits, faucets and Visual Studio plugins to attract developers. 

**Other partner chains**

A candidate to be partner chain is World mobile who need a purpose-built blockchain with a degree of centralization to meet regulations around spectrum licensing[^97] and satisfy the International Telecoms Union’s requirements. SingularityNET could also potentially launch a decentralized LLM[^98] as a partner chain. With so many new acronyms and announcements, Hoskinson clarified[^99]

>There's two projects at the same time, Cardano partner chain toolkit and Midnight. One is downstream of the other …Midnight is downstream of the partner chain toolkit, and there's a separate team that works on that… they're both in Rust, with heavy modifications, but one is a blockchain builder kit, and its intention is to build out the partner chain ecosystem and the other is specifically Midnight

As we started the chapter talking about Layer 1s, Layer 2s, state channels and sidechains…it can all get a bit confusing as to where a partner chain begins and ends. Hoskinson added further clarity:[^100]

>So 'cause I often get asked a question ‘is Midnight a layer 2 or a sidechain?’ …I say it's neither and both…it’s neither in that it does not rely solely on the security of the main chain, for its security, and it doesn't rely on itself for its security. It actually borrows from both, and you can run multiple consensus algorithms at the same time. So ideally I'd like to blend useful proof of work on Midnight with a BFT protocol enabled by the stake pool operators of Cardano. And how do all of those pieces come together? …that's why I say there's kind of three parts. There's a Cardano part, there’s a framework part and then there’s a Midnight-specific part… and that’s going to take a little while to sort it’s way out.
>
>But the other cool thing is that these things always benefit each other. So when we talk about Input Endorsers, a lot of the ideas that we're learning from partner chains are kind of being taken for a test drive, that could then be applied with the design of Input Endorsers and the long term sharding and scalability of Cardano's main chain. So when these SPOs are running this, we're learning a lot that can then be used to actually run and accelerate Cardano transactions and basically make our network have a much higher native TPS rate, and so it's all interconnected in in that respect

The Partner Chains strategy seems to be betting on arguably the most successful features of Cardano to date, its consensus and staking mechanism and the implementation of *Minotaur* being a game changer. Unlike any of the popular cloud service providers, Cardano has never been down since its first block was minted in 2017. Its liquid, non-custodial staking mechanism is years ahead of its time. Hoskinson describes the *Minotaur* paper as ‘probably the best thing we've ever written in the history of our company… because this ends the fight forever about interoperability’.

Visit *midnight.network* for more information  

## Input Endorsers 

By separating transactions into pre-constructed blocks, input endorsers increase block propagation speeds and throughput (amount of data transferred). This increases block propagation consistency and enables increased transaction rates.

Input endorsers were described by John Woods (ex IOG, now Algorand CTO) as a ‘near end game solution’ for Layer 1 scaling that will put Cardano on the top of the pile when it comes to throughput for Layer 1.

The current process is to scoop transactions out of mempool, forge a block, then send it on to peers. With input endorsers, blocks will be created on an ad hoc basis, signed and counter-signed, and will be flying around the network on a near second-by-second basis.

The existing network Ouroboros Praos, where a block is generated every 20 seconds, is adequately meeting user demands. Input Endorsers will, however, keep Cardano ahead of the curve for the demands coming down the tracks with more and more businesses deploying on Cardano, as Plutus and Marlowe mature.

Currently, blocks are responsible for both consensus and holding transaction data. Input Endorsers divide each block in two. One of the blocks is responsible for consensus, with the other faster block assigned for holding transaction data.

The consensus block will essentially be freed up from its duty of managing transaction data. It will now have a pointer (using ‘reference semantics’) to the block holding the transaction data. This will reduce bottlenecks and the 20 second wait time, enabling blocks to be streamed constantly.

Input Endorsers were muted as far back as the original Ouroboros paper in 2016. Similar to block producers (BP), input endorsers (IE) are described as a stakeholder entity, in the sense that the amount of stake delegated to them affects their capacity to function. 

According to Section 8.1 of the paper: 

>Input-endorsers create a second layer of transaction endorsing prior to block inclusion. [..] Note that input-endorsers are assigned to slots in the same way that slot leaders are, and inputs included in blocks are only acceptable if they are endorsed by an eligible input-endorser.

and also

> Note that blocks and endorsed inputs are diffused independently with each block containing from 0 up to d endorsed inputs.

IOG researcher Peter Gaži explained the input endorsers concept[^101] at the Cardano Summit 2021. Input endorsers echo some concepts discussed in a paper called *Prism: Scaling Bitcoin by 10,000x*[^102] which is complemented by a video presentation[^103] on *Prism* (not to be confused with IOG’s Atala Prism Decentralized Identity solution).

Professor Aggelos Kiayias gave a more detailed explanation in his video[^104] whose formulas and math are beyond the scope of this book. It’s clear, however, that input endorsers are kind of an anthology of the best of Cardano as they leverage the power of Mithril, the Extended UTXO model, previous research on ledger combiners and the foundations established by Ouroboros.

In the video, Prof Kiayias explained Ouroboros uses a ‘longest chain’ protocol[^105] similar to Bitcoin, except it is based on proof of stake.[^106] So it inherits all the decentralization and security benefits of Bitcoin, but with much less energy expenditure. ‘Longest chain’ protocols have serious performance limitations in terms of throughput. If a pipe represents a consensus protocol, where width is the throughput and length is the settlement time, then we want a nice wide, short pipe.

Based on research IOG[^107] published at the *ACM Computer and Communications Security Symposium* in 2021, it’s possible to derive the upper bound for the throughput in a longest chain protocol. This works out to be only 8%, leaving 92% of the throughput capacity untapped. Ouroboros *Leios*, and specifically input endorsers, will resolve this critical shortcoming. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig88.png "figure 8.8")
<br>**Figure 8.8:** Longest chain protocol represented as a pipe

As mentioned previously, Ouroboros uses a networking strategy of applying *backpressure* to cope with times when there is peak demand for transaction processing. The system processes what blocks it can, while transactions wait in line to be pulled in for processing. Under peak traffic conditions, transactions will still be processed, but they have to wait their turn.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig89.png "figure 8.9")
<br>**Figure 8.9:** Backpressure networking concept 

Input endorsers release segments of mempool (or ‘backup mempools with special privileges’ as a user on Stack Exchange[^108] referred to them) to float around before they’re considered for processing in a mainchain block. These floating segments of mempool are called ‘input blocks.’ This allows block producers to free up space in their mempools so they have more capacity to pull transactions in. Mempool segmentation needs to be concurrent across all block producers.

IOG plans on adopting practices from spread spectrum communications[^109] to ensure there is minimal overlap between input blocks. Valid input blocks are checked as with longest chain blocks, but additionally, they are attested via the issuance of Mithril certificates. This means input blocks are transformed into verified transaction batches to be included in the mainchain by reference only. Input blocks’ transactions and scripts are processed externally from the mainchain block validation. Longest chain ‘ranking blocks’ are used to organize or ‘rank’ these floating input blocks.

The serialization nature of longest chain protocol resolves ‘double-spending’ in input blocks. This strategy also leverages the strengths of the Extended UTXO model as script execution and validation occurs away from mainchain validation. The goal of higher 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig810.png "figure 8.10")
<br>**Figure 8.10:** Input Endorsers graphic adapted from Professor Kiayias explainer video

How this groundbreaking academic research will go from theory to a real-life implementation became a little clearer in November 2022. Input endorsers will be the primary component of Ouroboros Leois and will be proposed, community-reviewed and finalized via CIP 79. As we are now in the ‘age of Voltaire’, everything is open source, encouraging feedback and participation. *Leios* will be a ‘substantial extension’ of the Ouroboros protocol. It is described in greater depth in a longer paper[^110] included as part of this CIP.

The paper is also available on GitHub[^111] and is surprisingly readable. This is perhaps by design to attract as much discussion and engagement as possible in the initial stages. It was written by IOG chief architect Duncan Coutts, often described as a ‘real life wizard’ by Charles Hoskinson. You can peer inside his mind and follow the debate with other deep thinkers such as nuclear physicist Michael Lisenfelt here.[^112]

The paper details exactly how input endorsers might work. At a high level, the research proposes moving from a sequential blockchain to a parallel blockchain. *Leios* will decouple the consensus from the validation of blocks, meaning blocks will be validated constantly. 

With the current Ourorboros Praos protocol, the time during which a block is forged and diffused across the network is only a fraction of the overall average time between blocks. Currently on Cardano mainnet: blocks are produced on average every 20 seconds, but the time to send blocks across the network is within 5 seconds (this is the ∆ parameter).

Before the block arrives at a node, that node is idle, and after it has downloaded, validated and forwarded the block then it will return to being idle. *Leois* proposes different ways to make better use of idle resources.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig811.png "figure 8.11")
<br>**Figure 8.11:**  Ouroboros Praos block diffusion time (∆) is a fraction of time between blocks 

A distributed system of nodes is a parallel system, but Ouroboros Praos is a sequential algorithm. Any such sequential algorithm running on a parallel system will leave resources unused. The algorithm is sequential because the structure of the blockchain itself is linear.

Ouroboros *Leios* will attempt to deploy a ‘concurrent blockchain’ to achieve a parallel distributed algorithm for constructing the chain. By controlling the degree of concurrency and parallelism in the algorithm, this will enable larger workloads where currently unused idle resources are put to work. The paper clarifies the terms: 

>We distinguish concurrency and parallelism: concurrency is about data or events that are not sequenced with respect to each other, whereas parallelism is about using more computer hardware to compute more quickly.

The paper goes into greater detail on how this could be achieved with new types of objects such as input blocks, endorsement blocks, endorsement reports, endorsement certificates, and ranking blocks. The above linked paper and CIP outline the many considerations and risks with such a complex solution and will no doubt evolve and update as further prototyping and simulation eventually arrives at the best design. The first such public simulation was presented by Benjamin Beckmann (IOG Director of Architecture & Infrastructure) at ScotFest.[^113]

The exhaustive process will follow the familiar trail of security analysis, peer review, auditing, formalization a precise description of the expected behaviors to clarify the design to engineering, performance testing, prototyping, updates to the ledger…and all this is dependent on progress with other features such as ‘On disk storage of ledger state’, a successful Ouroboros *Genesis* rollout, increased adoption of light wallets, etc.  

Only then will a hard fork to *Leios* be possible. It is an ambitious vision, but IOG and the Cardano community are building on granite, reaping the rewards of doing things the right way from the start. All the features and concepts described in this book are anchored in deep academic research, peer-reviewed by the brightest minds in cryptography and implemented based on formal specifications. 

**Oct 3, 2022. Re: Input Endorsers, Let’s Talk Basho.** CH[^114]

>So, what happens is that you go from this standard process of a chain of blocks, and there's only one canonical view, to basically, doing a lot of these things asynchronously and in parallel, and they just kind of get batched together, and then asynchronously and in parallel, lots of stuff happens and then they get batched together… So, this concept of input blocks and key blocks, as discussed in our parallel chains paper.[^115]
>
>Now this batching…you think of Mithril certificates where you talk about batching transactions, events together …you also could reuse this technology in the extended UTXO model to patch blocks together. So, it gives you a way of figuring out conflict-free history, and potentially what this means is that you have asynchronous parallel processing of an enormous amount of events. So, the throughput gains, assuming new data structures, and assuming new designs, are gargantuan for this because you basically can be real time, continuously running computations. Right now, in the current design, only 0.25% of your block time budget is for computation.
>
>So, running execution of scripts… so that's incredibly limiting …0.25%, not 25%, but 0.25% of your block time is for script execution, so it's a very scarce resource. Here it's asynchronous, so it's continuous execution. So, we expect to see not just a 10x, but a very very very significant increase in speed, and a reduction in cost…


**_To be uploaded soon..._**

[^01]: Protocol parameters, cexplorer.io/params
[^02]: Performance engineering: Lies, damned lies and (TPS) benchmarks, youtube.com/watch?v=gpSnyCn2s9U
[^03]: Cardano became the most developed crypto project on GitHub in 2021, cointelegraph.com/news/cardano-became-the-most-developed-crypto-on-github-in-2021-santiment
[^04]: Cardano Surpasses Ethereum In GitHub Daily Development Activity, investing.com/news/cryptocurrency-news/cardano-surpasses-ethereum-in-github-daily-development-activity-2956870
[^05]: Cardano Review 2024, coinbureau.com/review/cardano-review/#cardano-developer-ecosystem
[^06]: Tim Harrison, ‘How we are scaling Cardano in 2022’, iohk.io/en/blog/posts/2022/01/14/how-we-re-scaling-cardano-in-2022/
[^07]: Basho, Input Endorsers, and the Future of Scalability, youtube.com/watch?v=EYc7r5s8cco
[^08]: **Resident set size (RSS)** is the portion of memory occupied by a process that is held in main memory (RAM).
[^09]: Cardano node release notes, github.com/IntersectMBO/cardano-node/releases
[^10]: **Regression testing** is re-running tests to ensure that previously developed and tested software is performing as expected after a change.
[^11]: @SmaugPool, twitter.com/SmaugPool/status/1737814894710231161
[^12]: CIP-0??? | Plutus v1 compatible script references, github.com/cardano-foundation/CIPs/pull/679
[^13]: PCP_max_tx_ex_mem_PiLanningham, forum.cardano.org/t/pcp-max-tx-ex-mem-pilanningham/125506
[^14]: PCP_max_block_size_RichardMcCracken, forum.cardano.org/t/pcp-max-block-size-richardmccracken/125507
[^15]: **Block header**: The portion of a block that contains information about the block itself (block metadata), typically including a timestamp, a hash representation of the block data, the hash of the previous block's header, and a cryptographic nonce (if needed).
[^16]: **RAM (random-access memory)** is a form of computer memory that can be read and changed in any order, typically used to store working data and machine code. A random-access memory device allows data items to be read or written in almost the same amount of time irrespective of the physical location of data inside the memory.
[^17]: Draft UTxO HD design document for review, github.com/input-output-hk/ouroboros-network/commit/f4f9be4f73a4f4cc31e98ec6a0511d9c7e9a4601
[^18]: Wust, et al, (2019), 'ACE: Asynchronous and Concurrent Execution of Complex Smart Contracts', eprint.iacr.org/2019/835.pdf
[^19]: Cardano Summit 2021, youtube.com/watch?v=rmknjCvRH-Y
[^20]: Chaidos, Kiayias (2021), 'Mithril: Stake-based Threshold Multisignatures', eprint.iacr.org/2021/916.pdf 
[^21]: Mithril Release Process, mithril.network/doc/dev-blog/2022/12/05/release-process
[^22]: Mithril: a stronger and lighter blockchain for better efficiency, iohk.io/en/blog/posts/2021/10/29/mithril-a-stronger-and-lighter-blockchain-for-better-efficiency/
[^23]: Miken Hornan’s Simplified Mithril diagram, forum.cardano.org/t/new-mithril-diagram-by-mike-hornan/120568
[^24]: Cardano360 May 2022, youtu.be/Ar_8Lo0nV1s?t=228
[^25]: Light, fast, efficient, and secure - Mithril, youtube.com/watch?v=VyxsqwNWZt4
[^26]: Mithril SPO onboarding guide, mithril.network/doc/manual/getting-started/SPO-on-boarding-guide/
[^27]: Approximate Lower Bound Arguments, eprint.iacr.org/2023/1655
[^28]: @IOHK_Charles, twitter.com/IOHK_Charles/status/1719314519636254899
[^29]: Charles Hoskinson on Midnight, token airdrop to all ADA holders, and Cardano Governance!, youtube.com/watch?v=Ki-HSHgtIGk
[^30]: Closing Keynote- Looking Ahead to 2024 and Beyond, youtu.be/OzLdZxkfAeQ?si=jQ9Qu6Eg9c8-SUe9&t=172
[^31]: Weekly Development Updates, essentialcardano.io/development-update
[^32]: Mithril on GitHub, github.com/input-output-hk/mithril
[^33]: Isomorphism: corresponding or similar in form and relations.
[^34]: Prof Aggelos Kiayias, ‘Enter the Hydra: scaling distributed ledgers, the evidence-based way,’ iohk.io/en/blog/posts/2020/03/26/enter-the-hydra-scaling-distributed-ledgers-the-evidence-based-way/
[^35]: Sebastian Nagel, ‘Hydra – Cardano’s solution for ultimate Layer 2 scalability’, iohk.io/en/blog/posts/2021/09/17/hydra-cardano-s-solution-for-ultimate-scalability/
[^36]: Hydra Head roadmap, github.com/orgs/input-output-hk/projects/21/views/7
[^37]: Cardanians Hydra blog, cardanians-io.medium.com/hydra-cardano-scalability-solution-36b05ddc91cf
[^38]: TPS on crypto twitter, twitter.com/bitcoinissaving/status/1437240100807749633
[^39]: MMT Chakravarty, S Coretti, M Fitzi, P Gazi, P Kant, A Kiayias, and A Russell (2020) ‘Hydra: fast isomorphic state channels’(Section 7 – Simulations), eprint.iacr.org/2020/299.pdf 
[^40]: Hydra Head benchmarking, hydra.family/head-protocol/benchmarks
[^41]: Hydra for Payments, /en/blog/posts/2022/11/10/hydra-for-payments-introducing-developer-tooling-to-unlock-micropayments-on-cardano/
[^42]: SundaeSwap Labs Hydra demo, twitter.com/sundaeswap/status/1580969361892085762?lang=en
[^43]: Sebastian Nagel Hydra talk, summit.cardano.org/agenda-day-2/cardano-ballot-speaker-winner-presentation-6/
[^44]: Charles Hoskinson Interview: Your Cardano Questions Answered, youtu.be/PV_C17noXlA?t=3276
[^45]: The Lightning Network is a Layer 2 payment protocol that operates on top of a blockchain. It theoretically enables fast transactions between participating nodes and has been touted as a solution to the bitcoin scalability problem.
[^46]: Let's Talk Basho, youtu.be/fhVo-2QUjLM?t=460
[^47]: Hydra Head protocol: an open source solution for scalability, cardanofoundation.org/en/news/hydra-head-protocol-an-open-source-solution-for-scalability/
[^48]: Implementing auction projects using Hydra, iohk.io/en/blog/posts/2023/01/20/implementing-auction-projects-using-hydra/
[^49]: Hydra Support for Kupo, github.com/CardanoSolutions/kupo/pull/117
[^50]: Hydra node explainer, hydra.family/head-protocol/core-concepts/architecture/
[^51]: Hydra tutorial, github.com/input-output-hk/hydra/issues/997
[^52]: Hydra mainnet release, twitter.com/ch1bo_/status/1656679454570340355
[^53]: Hydra voting poc, github.com/cardano-foundation/hydra-voting-poc
[^54]: November 2023 Monthly Review Meeting, drive.google.com/file/d/1-iv8IveUzA2KrJV_Kqrgx4ts05Ow0zjM/edit
[^55]: Hydra Head roadmap, github.com/orgs/input-output-hk/projects/21
[^56]: Jourenko, Larangeira, TanakaInterhead Hydra Two Heads are Better than One, eprint.iacr.org/2021/1188
[^57]: Adam Back, et al (2014) 'Enabling Blockchain Innovations with Pegged Sidechains', blockstream.com/sidechains.pdf
[^58]: Scorex project, github.com/input-output-hk/Scorex
[^59]: HyperLedger Labs, ScoreX, labs.hyperledger.org/labs/archived/scorex.html
[^60]: Hackers have stolen $1.4 billion this year using crypto bridges, cnbc.com/2022/08/10/hackers-have-stolen-1point4-billion-this-year-using-crypto-bridges.html
[^61]: Gazi, Kiayias, Zindors (2019), ‘Proof-of-Stake Sidechains’, iohk.io/en/research/library/papers/proof-of-stake-sidechains/
[^62]: A **Byzantine fault** is any fault presenting different symptoms to different observers. A Byzantine failure is the loss of a system service due to a Byzantine fault in systems that require consensus among distributed nodes.
[^63]: IOG launches a toolkit for developing custom sidechains on Cardano, iohk.io/en/blog/posts/2023/01/12/iog-launches-a-toolkit-for-developing-custom-sidechains-on-cardano/
[^64]: Sidechain SDK docs, docs.cardano.org/cardano-sidechains/sidechain-toolkit/introduction
[^65]: Cardano: the problem & the whitepaper to fix it, youtube.com/watch?v=LIEM6qbc-x8
[^66]: Milkomeda dApps, milkomeda.com/dapp-store
[^67]: Sebastien Guillemot Milkomeda Update, youtube.com/watch?v=LlxTmDPw_cs
[^68]: Milkomeda Oracle, cardano.ideascale.com/c/idea/369192
[^69]: StakeWithPride re: Ethereum zk roll-ups, twitter.com/StakeWithPride/status/1607511445549514752
[^70]: The core idea of SGX is the creation of a software 'enclave'. The enclave is basically a separated and encrypted region for code and data.
[^71]: Orbis: Layer 2 ZK Rollup, cardano.ideascale.com/c/idea/396617
[^72]: April 20, 2022, ‘4/20 Hangout with Charles’ Twitter space, twitter.com/i/spaces/1lDGLLABeBkGm
[^73]: Temujin Louie, 'Guest blog: collaborating on Cardano interoperability', iog.io/en/blog/posts/2022/04/27/guest-blog-collaborating-on-cardano-interoperability/
[^74]: Rollups on Cardano Discussion | Cardano Live #48, youtube.com/watch?v=4DslvkLop04
[^75]: Maller, Bowe, Kohlweiss, Meiklejohn (2019), 'Sonic: Zero-Knowledge SNARKs from Linear-Size Universal and Updateable Structured Reference Strings', eprint.iacr.org/2019/099.pdf
[^76]: Kerber, Kiayias, Kohlweiss (2021) 'Kachina - Foundations of Private Smart Contracts', eprint.iacr.org/2020/543.pdf
[^77]: Charles Hoskinson Kachina tweet, twitter.com/iohk_charles/status/1261328840023961602?lang=en
[^78]: Zexe: Enabling Decentralized Private Computation, eprint.iacr.org/2018/962.pdf
[^79]: Cardano Midnight: Monero Retracts Negative Statements, u.today/cardano-midnight-monero-retracts-negative-statements
[^80]: A dead man's switch is a switch that is designed to be activated or deactivated if the human operator becomes incapacitated, or dies. Typically, funds may be sent to a preset address after a set time has expired.
[^81]: MPC (multi-party computation) enables multiple parties – each holding their own private data – to evaluate a computation without ever revealing any of the private data held by each party.
[^82]: The top programming languages, statista.com/statistics/793628/worldwide-developer-survey-most-used-languages/
[^83]: New Years Eve Hangout with Charles, twitter.com/IOHK_Charles/status/1609417098396323840?t=42JFCPU8bk_mbwlix8wGlw&s=19
[^84]: Midnight Special, youtube.com/watch?v=tBxk79svC78
[^85]: Cardano Settlement Layer, why.cardano.org/en/introduction/designing-in-layers/
[^86]: Cardano Computation Layer, why.cardano.org/en/introduction/cardano-computation-layer/
[^87]: Microservices are an architectural approach where software is composed of small independent services that communicate over well-defined APIs. Service-oriented architecture (SOA) focuses on discrete services instead of a monolithic design
[^88]: Cardano As The Center Of The Universe, cexplorer.io/article/cardano-as-the-center-of-the-universe
[^89]: Parity Substrate, substrate.io/
[^90]: A parachain on Polkadot is similar to a sidechain. They are named after the notion of parallelized chains running parallel to a Relay Chain.
[^91]: Latest Cardano and Crypto Developments with Charles Hoskinson, 14 Dec 2023, twitter.com/i/spaces/1YqxoDPoMdaKv
[^92]: BABE protocol, research.web3.foundation/Polkadot/protocols/block-production/Babe
[^93]: Fitzi, Kiayias, et al. (2022) 'Minotaur: Multi-Resource Blockchain Consensus', dl.acm.org/doi/pdf/10.1145/3548606.3559356
[^94]: Babel fees - denominating transaction costs in native tokens, iohk.io/en/blog/posts/2021/02/25/babel-fees/
[^95]: Supernode concept, hyperledger.github.io/firefly/overview/supernode_concept.html
[^96]: CEO of Midnight on Tokens for ADA Delegates, and what Midnight offers Cardano users! | Eran, youtube.com/watch?v=ZBMj0srAAfw
[^97]: Spectrum licensing refers to the process of allocating specific frequency ranges, or spectrum bands, to telecommunication service providers.
[^98]: LLM, or Large language models, are a type of AI that can mimic human intelligence
[^99]: Surprise AMA 11/26/2023, youtube.com/live/2ItsXSY2qfA?si=bXZAoFVGvcGJQq1-&t=504
[^100]: Latest Cardano and Crypto Developments with Charles Hoskinson, 14 Dec 2023, twitter.com/i/spaces/1YqxoDPoMdaKv
[^101]: Surprise AMA 11/26/2023, youtube.com/live/2ItsXSY2qfA?si=bXZAoFVGvcGJQq1-&t=504
[^102]: Latest Cardano and Crypto Developments with Charles Hoskinson, 14 Dec 2023, twitter.com/i/spaces/1YqxoDPoMdaKv
[^103]: Ouroboros Family (Input Endorsers), youtu.be/PF1SW7e137A?t=1760
[^104]: Prism: Scaling Bitcoin by 10,000x, arxiv.org/abs/1909.11261
[^105]: Presentation, Prism: Scaling Bitcoin, youtube.com/watch?v=gTJyDtuWvUQ
[^106]: Advances in Ouroboros: Scaling for Future Growth, youtube.com/watch?v=xKv94MwSNBw
[^107]: The longest chain is what individual nodes accept as the valid version of the blockchain. The rule that nodes adopt the longest chain of blocks allows every node on the network to agree on what the blockchain looks like, and therefore agree on the same transaction history. The Longest Chain Rule ensures that the network will recognise the ‘chain with most work’ as the main chain. The chain with the most work is typically (not always) the longest of the forks.
[^108]: Proof-of-Stake Longest Chain Protocols: Security vs Predictability, tselab.stanford.edu/downloads/PoS_LC_SBC2020.pdf
[^109]: Gaži, Kiayias, Russell (2020), 'Tight Consistency Bounds for Bitcoin', eprint.iacr.org/2020/661.pdf
[^110]: Input Endorsers on stack exchange, cardano.stackexchange.com/questions/4626/what-are-input-endorsers-and-how-do-they-make-cardano-more-scalable
[^111]: In telecommunication and radio communication, spread-spectrum techniques are methods by which a signal generated with a particular bandwidth is deliberately spread in the frequency domain, resulting in a signal with a wider bandwidth.
[^112]: Coutts, Panagiotakos, Fitzi (2022), 'Ouroboros Leios: design goals and concepts', iohk.io/en/research/library/papers/ouroboros-leios-design-goals-and-concepts/
[^113]: CIPs/CIP-0079/README.md, github.com/cardano-foundation/CIPs/blob/ouroboros-leios/CIP-0079/README.md
[^114]: CIP-0079? | Implement Ouroboros Leios to increase Cardano throughput, github.com/cardano-foundation/CIPs/pull/379
[^115]:  Driving continued technology advancement through Input Endorsers, youtube.com/watch?v=IGu_1bl6UHQ
[^116]: Let's Talk Basho, youtu.be/fhVo-2QUjLM?t=780
[^117]: Fitzi, Gaži, Kiayias, Russell (2018), 'Parallel Chains: Improving Throughput and Latency of Blockchain Protocols via Parallel Composition', iohk.io/en/research/library/papers/parallel-chains-improving-throughput-and-latency-of-blockchain-protocols-via-parallel-composition

