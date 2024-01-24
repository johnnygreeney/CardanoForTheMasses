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

-**Plutus requires resources**, both computational (CPU) units and memory units, in order to do useful things with a Plutus script. Plutus memory limitations can be extended, allowing for the creation of more complex Plutus scripts or allowing current scripts to handle more data items, enhance concurrency, and extend their capabilities. 

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
[^34]:
[^35]:
[^36]:
[^37]:
[^38]:
[^39]:
[^40]:

[^110]:
[^111]:
[^112]:
[^113]:
[^114]: Fitzi, Gaži, Kiayias, Russell (2018), 'Parallel Chains: Improving Throughput and Latency of Blockchain Protocols via Parallel Composition', iohk.io/en/research/library/papers/parallel-chains-improving-throughput-and-latency-of-blockchain-protocols-via-parallel-composition

