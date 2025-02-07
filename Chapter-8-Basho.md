# Chapter 8: Basho (Scaling on-chain)

*‘The journey itself is my home’* ― Matsuo Basho

**TO DO: add markdown format**

There are two eras left on the Cardano roadmap to discuss, and we’ll see over the next few chapters just how interconnected they are, and how, in practice, they will remain perpetual struggles as this emerging technology evolves. 
Scalability Defined

Cardano’s roadmap initially focused on establishing a decentralized, secure network. The innovative proof-of-stake model needed time to bed down and mature. There are now over 3,000+ stake pools confirming transactions, agreeing on the network state. This brings with it challenges in scaling a distributed system with no central, trusted nodes. The system must reach consensus to transfer assets, record of state and cryptographic proofs globally with constraints like network speed, differing hardware setups, etc.

Scalability is a blockchain’s ability to handle usage or adoption. Measuring scalability is not simply measuring the TPS (transactions per second) in any random scenario. Scalability is more nuanced than that. 

‘Yes, but can it do a million TPS?’ is a familiar refrain often used without any context on crypto twitter (X). TPS (transactions per second) is perhaps the crudest measure to use as a comparison out of all those available. Transactions occur in a variety of sizes and formats. While this is true for Cardano, it is much more important when comparing two systems that are so significantly different. More pertinent questions are… Can it handle demand today? Does it have a realistic roadmap to handle billions of users in future?

Scaling a blockchain means improving the blockchain design using the various techniques and features outlined in this chapter. Many of them are complementary and interdependent on each other. The overall goal is to increase throughput. Digging deeper, this means improving performance based on these metrics:

Throughput: the quantity of data that a system can process in a given length of time. Measured in Bytes per second (kilobytes per sec, kB/s) 
CPU seconds (milliseconds) ms/s per wall clock for script execution time, ie. how long was the CPU busy for. 
Finality: the amount of time it takes for an action’s consequence to become immutable and true for everyone in the system
Concurrency: the amount of work that various actors can do without interfering with one another.
Size of transaction(s)

At time of writing, blocks on the Cardano mainnet are created approximately every 20 seconds, with a max block size of 90kB and max transaction size of 16kB. You can review all the latest parameter settings on cexplorer. 

Any blockchain can appear fast and sexy using tiny transaction sizes and no scripts. Some high profile blockchains have centralized characteristics such as a minority of validators controlling disproportionate amounts of stake. It’s easy for a blockchain to compromise on decentralization then boast astronomical TPS figures, but if it needs to be stopped and restarted regularly, it should be a clue that it’s not really what it seems.   

You can configure protocols to maximize throughput, but throughput means something different in a UTxO system than it does in an account-based system. TPS on Cardano is yet more nuanced due to its native asset standard. eUTxO allows hundreds, even thousands, of native assets to be transferred in a single transaction. A more accurate metric is TPT (transactions per transaction). eUTtxO.org is a blockchain explorer created by Peter Oravec. It is an excellent learning tool to understand and visualize how transactions work on Cardano. 




Figure 8.1:  @oravecpeter tweets about eUTtxO.org ‘There are 923 outputs of these two transactions, each output can be different recipient so 923 TX... this is superpower of UTxO... everyone will use this because it's super cheap to do all this stuff in single TX...’ 

Unlike many blockchains who adopt a ‘move fast and break things’ approach, Cardano has always stuck to a deliberate, careful and methodical strategy. Despite this relative conservatism, Cardano was the most developed crypto project on GitHub in 2021, 2022, yet again in 2023 and was on track for a repeat in 2024.

IOG outlined their Basho strategy in a 2022 blog post and Charles Hoskinson gave an update in his July 2023 video Basho, Input Endorsers, and the Future of Scalability. 

Nearly everything on Cardano occurs as a transaction, and generally speaking resources are consumed from these types of activities…transferring ada, issuing assets, executing smart contracts, voting, adding metadata …and you can usually break it into three broad categories and so you have network, you have data storage, and then you have computation.

There is no ‘magic bullet’ for scaling blockchains, it’s done by tweaking parameters and combining different solutions that generally fall into two categories:
Layer 1 solutions: upgrades applied to the mainchain protocol, cardano-node, etc. 
Layer 2 solutions: offloading workloads, extending functionality and integrating other blockchains with sidechains, ZK rollups and state channels like Hydra.
So far, Cardano has scaled to meet demand, given its ambitious goal and numerous constraints. Changes made since the Vasil hard fork have borne fruit however DeFi and RealFi will begin in earnest in the coming bull market cycle. There are several stablecoins launching, Oracles like Charli3 will mature, partner chains coming, almost 2,000 projects building on Cardano with over 10 million native assets minted. 
 
Scaling solutions are usually categorized as either On-chain solutions which encompass block size increases, pipelining, input endorsers, parameter adjustments, Plutus script enhancements, node enhancements and on-disk storage improvements. Then there are Off-chain solutions including sidechains, partner chains, Hydra, off-chain computing. Mithril and the highly anticipated ZK Rollup projects newly enabled since the Chang hard fork. 
Ongoing enhancements

As part of the Basho development phase, parameters need to be tweaked. A flexible infrastructure that can bend, but not break, is key as conditions change. Some considerations when making changes are:

Increased block size enables more transactions to be fitted in a block. During times of network saturation, there will be reduced waiting time for transactions to be accepted by a block, which is a positive. There is, however, a cost. It takes longer for larger blocks to propagate throughout the network. Nodes will also need additional time to validate transactions as a result of this. Although increasing the block size might improve network speed, such adjustments should be done with care. It’s important to progressively alter settings and monitor the outcomes during high saturation times to guarantee that the increase does not impact block adoption time. 


Block level limit: increasing the amount of memory units (abstract memory units) available to each script in the block. Scripts express various kinds of logic in order to spend UTxOs. 


Mempool size: The size of the mempool is continually tweaked. When adding transactions to a block, the mempool acts as a network buffer and may cause a little delay. However, increasing the size of the mempool will not boost network throughput since transaction queues would remain the same. The mempool enables for a fair adoption of new transactions that arrive at random


Plutus requires resources, both computational (CPU) units and memory units, in order to do useful things with a Plutus script. Plutus memory limitations can be extended, allowing for the creation of more complex Plutus scripts or allowing current scripts to handle more data items, enhance concurrency, and extend their capabilities. 

Timeliness consideration when increasing throughput:

Timeliness: the time it takes to adopt a block. The entire ‘budget’ for block adoption is set at 5 seconds for a block to spread through 95% of the network, with Plutus scripts having a budget in the milliseconds. This is done to avoid monopolization by allowing the block to contain both scripts and simple transactions. 

Throughput:  Users will experience longer block adoption times if the number of blocks is raised dramatically all at once. That’s because throughput and timeliness are at odds: boosting throughput means greater network performance, but it might come at the expense of delays when the system is overburdened.

Congestion is minimized by efficient systems. Cardano’s network utilizes ‘backpressure’ to control overall system stress. While certain individual users may report higher transaction wait times during a big NFT drop, this does not indicate that the network is ‘struggling.’ It really signifies that the network is working properly, in what’s known as graceful degradation.

Ouroboros (Praos) has precise criteria that must be fulfilled to achieve its security objectives, with block propagation time being a priority. Block propagation time refers to how long it takes for a newly minted block to be propagated through 95% of the staked ada nodes on the network. For Praos to remain secure, new blocks must be propagated every 5 seconds.

Most parameter updates have side effects. For example, increased block size would automatically lengthen the time it takes to propagate blocks; thus, any modifications must be monitored to ensure increased speed doesn’t jeopardize network security. This 5 second budget will be expanded in future Ouroboros iterations. 

Node (cardano-node) enhancements  

The node is central to everything in Cardano. It stores a full copy of the blockchain, processes ledger rule and plutus scripts, creates transactions and certificates, distributes (diffuses) transactions and blocks across the network. It calculates and distributes staking rewards to the delegators directly as well as to the stake pools. The node ensures decentralization as 3,000+ stake pool operators run the node. When you use your wallet, you are using the node. So, a lot is going on under the hood to make the chain work. It makes sense, then, to improve the node’s performance where possible.

Improvements allow for a more uniform distribution of stake and reward calculations over epochs, allowing for larger block sizes. Memory use is also more efficient overall. Memory compression minimizes RSS footprint, while memory sharing reduces the amount of data that needs to be instantiated. 

As Node updates come thick and fast, it’s best to check the release notes for the very latest.

Plutus V2 enhancements   

At ScotFest in Edinburgh, Andrew Sutherland (Plutus Compiler Team Lead), reviewed the year since PlutusV1 was launched and subsequently enhanced with V2 in September 2022. The various enhancements made with the Vasil hard fork led to faster core interpreter, faster untyped Plutus Core execution and lower transaction fees. Sutherland credited the CIP process as the steering force behind the progress. 

MuesliSwap (muesliswap.com), the first native DEX on Cardano, took part in a benchmarking case study for Plutus V2 scripts. The results were a 90% reduction in transaction size and a 50% saving on transaction fees. 

The CIP 49 ‘SEC P’ Valentine hard fork in February 2023 opened up a new world of interoperability options. These are crucial building blocks for bridge security, among other use cases. 

As 2023 drew to a close, there were concerns expressed regarding Cardano’s ability to scale in the next bull market. SM₳UG observed '40% of Cardano blockchain, 60/150 GB are PlutusV1 scripts duplicated over & over again.arm’ because scripts can't be referenced in Plutus V1 and must be included again each time they're used. Pi Lanningham submitted a CIP proposing a backwards compatible way to support script references in Plutus V1 scripts. 

On the Cardano Forum, Pi also wrote up his reasons for tweaking parameters to prepare for increased DeFi activity. Meanwhile, Rick McCraken also posted a PCP (protocol change proposal) making a case for a block size increase.

Plutus V3, which brought additional governance and voting functionality but also enhanced Plutus Core's cryptographic capabilities enabling new possibilities, including:


Interoperability between blockchains
Support for porting Ethereum smart contracts to Cardano
Sidechain bridges
A “Sum of products” which brings support for direct encoding of data types, meaning smaller, more efficient, scripts.  

For more details on these new cryptographic primitives, see CIP-58 and CIP-85.

You should be coming round to the notion that everything is related in Cardano. Many of the solutions discussed in this chapter require a hard fork to implement changes to the base protocol. Deciding on which parameters to change, when to execute updates, and by whom, can lead to robust discussions. Opposing views and priorities are inevitable as the ecosystem grows. Governance was gradually transitioned from the genesis entities to the wider community in 2024 and fully enabled with the Plomin hard fork in 2025. How do we debate key issues and decide a path forward is the subject of the next chapter. 
Pipelining

Before Pipelining was introduced, a block was minted by an SPO, that’s a new block in the blockchain that had to be validated and sent onto a peer. The problem was that peers also had to validate it and then send it onto their peer and that’s how the blocks diffused across the network.

By combining validation with propagation, the time it takes for a block to propagate is reduced. By minimizing the ‘dead time’ between blocks, the objective is for blocks to be propagated to at least 95% of peers within 5 seconds (block propagation overhead). This allows flexibility to make other scaling adjustments, such as raising block size, or other Plutus parameter limits.

Pipelining is a natural progression of Cardano’s ‘plumbing’. It’s an important part of the scaling strategy, and a logical approach to ramping up Cardano’s capacity as the ecosystem expands. Each update is carefully monitored and reviewed for at least one epoch (5 days) before proceeding with subsequent changes. A decentralized network architecture must be scaled depending on real-world usage, notwithstanding the substantial research and technical effort that has gone into creating and installing the system.

Diffusion pipelining

Pipelining, or more specifically, diffusion pipelining, is a consensus layer innovation that allows for speedier block propagation. It allows for more headroom, allowing Cardano’s performance and competitiveness to improve even more. It’s important to understand the system behavior of how blocks propagate, to see how this strategy accomplishes its purpose.

As it passes around the chain, a block goes through 6 stages:

Block header transmission
Block header validation
Block body request and transmission
Block body validation and local chain extension
Block header transmission to downstream nodes
Block body transmission to downstream nodes

The path of a block is highly sequential. At each node, all steps occur in the same order every time. Block transmission takes a long time due to the large number of nodes and the ever-increasing quantity of blocks. Diffusion pipelining layers some of the above stages on top of one another, allowing them to happen simultaneously. This takes less time and boosts throughput.


Figure 8.2: Pipelining (courtesy of @jJosjuaThreatt tweet)

The time savings provided by this technique will allow Cardano to expand even further, including adjustments to:

Block size – the larger the block, the more transactions, and scripts it can accommodate
Plutus memory limitations - the maximum amount of memory that a Plutus script may use
Plutus CPU limits - a script may be given extra computing resources to execute more effectively.

Pipelining makes sure that the block header referencing the hash of a previous block is propagated correctly. Metadata included in the next block contains the body of the previous block. This is a safeguard to prevent DDoS (distributed denial of service) attacks even without full block confirmation.

From theory to practice

Diffusion pipelining was created with the goal of achieving quicker block propagation while avoiding ‘destructive’ alterations to the chain. Because nodes depend on these current approaches, IOG did not want to eliminate any of the protocols, primitives, or interactions currently in use in Cardano. Instead of modifying how things operate now, they’re establishing a new mini protocol whose purpose is to pre-notify subscribing entities when a new desired block is detected, prior to full validation. Implementing Pipelining didn’t require a hard fork and can be rolled out with a standard node release. It was introduced without fanfare the same time as the Vasil hard fork.

The ability to pre-notify peers and provide them a block before it is verified, allowing the downstream peer to pre-fetch the new block body, is the most significant feature brought by pipelining. This saves a lot of time since the time it takes to verify a block over several hops is reduced significantly. The network was stress tested post-Vasil and the initial results were very positive. The node is now running faster, with more throughput. 



Figure 8.3: Tweet from Rick McCracken post-Vasil
On-disk storage
The Cardano node needs RAM when it’s running. It’s prudent to start moving things out of RAM, out of that expensive volatile memory into on-disk storage. This is a common practice in computer science. On-disk storage will improve the user experience for developers on Cardano.

By storing elements of the protocol state on disk, nodes will use less memory, allowing RAM-starved systems to operate nodes as long as they have enough storage, and memory will no longer be a scaling restriction. The blockchain state will be able to increase significantly as a result of this.

There is a ‘UTxO HD’ project ongoing to move Cardano’s ledger state from being completely in-memory to being stored more on-disk. This is required to be able to scale to larger ledger states. It will also naturally ease RAM requirements for nodes. This feature will enable other roadmap items, such as parts of Ouroboros Genesis, Peras and ultimately Leios.

In 2024, the consensus team resumed work on implementing UTXO-HD as part of wider effort with other teams. As this topic is quite technical and beyond scope for beginners, it’s best to refer to the performance and tracing updates where Well-Typed and other contributors post milestones and testing results. There is also the archive of development reports  for those interested in digging deeper.

Input Endorsers  

By separating transactions into pre-constructed blocks, input endorsers increase block propagation speeds and throughput (amount of data transferred). This increases block propagation consistency and enables increased transaction rates.

Input endorsers were described by John Woods (ex IOG, now Algorand CTO) as a ‘near end game solution’ for Layer 1 scaling that will put Cardano on the top of the pile when it comes to throughput for Layer 1.

The current process is to scoop transactions out of mempool, forge a block, then send it on to peers. With input endorsers, blocks will be created on an ad hoc basis, signed and countersigned, and will be flying around the network on a near second-by-second basis.

The existing network Ouroboros Praos, where a block is generated every 20 seconds, is adequately meeting user demands. Input Endorsers will, however, keep Cardano ahead of the curve for the demands coming down the tracks with more and more businesses deploying on Cardano, as Plutus and Aiken mature.

Currently, blocks are responsible for both consensus and holding transaction data. Input Endorsers divide each block in two. One of the blocks is responsible for consensus, with the other faster block assigned for holding transaction data.

The consensus block will essentially be freed up from its duty of managing transaction data. It will now have a pointer (using ‘reference semantics’) to the block holding the transaction data. This will reduce bottlenecks and the 20 second wait time, enabling blocks to be streamed constantly. 

Input Endorsers were muted as far back as the original Ouroboros paper in 2016. Similar to block producers (BP), input endorsers (IE) are described as a stakeholder entity, in the sense that the amount of stake delegated to them affects their capacity to function. 

According to Section 8.1 of the paper: 
Input-endorsers create a second layer of transaction endorsing prior to block inclusion. [..] Note that input-endorsers are assigned to slots in the same way that slot leaders are, and inputs included in blocks are only acceptable if they are endorsed by an eligible input-endorser.
also
Note that blocks and endorsed inputs are diffused independently with each block containing from 0 up to d endorsed inputs.

IOG researcher Peter Gaži explained the input endorsers concept at the Cardano Summit 2021. Input endorsers echo some concepts discussed in a paper called Prism: Scaling Bitcoin by 10,000x which is complemented by a video presentation on Prism (not to be confused with IOG’s Atala Prism Decentralized Identity solution).

Professor Aggelos Kiayias gave a more detailed explanation in his video whose formulas and math are beyond the scope of this book. It’s clear, however, that input endorsers are kind of an anthology of the best of Cardano as they leverage the power of Mithril (explained shortly), the Extended UTxO model, previous research on ledger combiners and the foundations established by Ouroboros.

In the video, Prof Kiayias explained Ouroboros uses a ‘longest chain’ protocol similar to Bitcoin, except it is based on proof of stake. So it inherits all the decentralization and security benefits of Bitcoin, but with much less energy expenditure. ‘Longest chain’ protocols have serious performance limitations in terms of throughput. If a pipe represents a consensus protocol, where width is the throughput and length is the settlement time, then we want a nice wide, short pipe.

Based on research IOG published at the ACM Computer and Communications Security Symposium in 2021, it’s possible to derive the upper bound for the throughput in a longest chain protocol. This works out to be only 8%, leaving 92% of the throughput capacity untapped. Ouroboros Leios, and specifically input endorsers, will resolve this critical shortcoming. 

   
Figure 8.4: Longest chain protocol represented as a pipe
As mentioned previously, Ouroboros uses a networking strategy of applying backpressure to cope with times when there is peak demand for transaction processing. The system processes what blocks it can, while transactions wait in line to be pulled in for processing. Under peak traffic conditions, transactions will still be processed, but they have to wait their turn.

Figure 8.5: Backpressure networking concept 

Input endorsers release segments of mempool (or ‘backup mempools with special privileges’ as a user on Stack Exchange referred to them) to float around before they’re considered for processing in a mainchain block. These floating segments of mempool are called ‘input blocks.’ This allows block producers to free up space in their mempools so they have more capacity to pull transactions in. Mempool segmentation needs to be concurrent across all block producers.

IOG plans on adopting practices from spread spectrum communications to ensure there is minimal overlap between input blocks. Valid input blocks are checked as with longest chain blocks, but additionally, they are attested via the issuance of Mithril certificates. This means input blocks are transformed into verified transaction batches to be included in the mainchain by reference only. Input blocks’ transactions and scripts are processed externally from the mainchain block validation. Longest chain ‘ranking blocks’ are used to organize or ‘rank’ these floating input blocks.

The serialization nature of longest chain protocol resolves ‘double-spending’ in input blocks. This strategy also leverages the strengths of the Extended UTxO model as script execution and validation occurs away from mainchain validation. The goal of higher throughput is now possible as the idle 92% capacity can now be utilized. The graphic below captures all the moving parts to input endorsers.

Figure 8.6: Input Endorsers graphic adapted from Professor Kiayias explainer video
How this groundbreaking academic research will go from theory to a real-life implementation became a little clearer in this 2024 video from Prof Aggelos Kiayias. Input endorsers will be the primary component of Ouroboros Leois and will be proposed, community-reviewed and finalized via a CIP. As we are now in the ‘age of Voltaire’, everything is open source, encouraging feedback and participation. Leios will be a ‘substantial extension’ of the Ouroboros protocol. It is described in greater depth in this research paper. 

The paper is also available on GitHub and is surprisingly readable. This is perhaps by design to attract as much discussion and engagement as possible in the initial stages. It was written by IOG chief architect Duncan Coutts, often described as a ‘real life wizard’ by Charles Hoskinson.  

The paper details exactly how input endorsers might work. At a high level, the research proposes moving from a sequential blockchain to a parallel blockchain. Leios will decouple the consensus from the validation of blocks, meaning blocks will be validated constantly. 
With the current Ourorboros Praos protocol, the time during which a block is forged and diffused across the network is only a fraction of the overall average time between blocks. Currently on Cardano mainnet: blocks are produced on average every 20 seconds, but the time to send blocks across the network is within 5 seconds (this is the ∆ parameter).

Before the block arrives at a node, that node is idle, and after it has downloaded, validated and forwarded the block then it will return to being idle. Leois proposes different ways to make better use of idle resources.

Figure 8.7:  Ouroboros Praos block diffusion time (∆) is a fraction of time between blocks 
A distributed system of nodes is a parallel system, but Ouroboros Praos is a sequential algorithm. Any such sequential algorithm running on a parallel system will leave resources unused. The algorithm is sequential because the structure of the blockchain itself is linear.

Ouroboros Leios will attempt to deploy a ‘concurrent blockchain’ to achieve a parallel distributed algorithm for constructing the chain. By controlling the degree of concurrency and parallelism in the algorithm, this will enable larger workloads where currently unused idle resources are put to work. The paper clarifies the terms: 

We distinguish concurrency and parallelism: concurrency is about data or events that are not sequenced with respect to each other, whereas parallelism is about using more computer hardware to compute more quickly.

The paper goes into greater detail on how this could be achieved with new types of objects such as input blocks, endorsement blocks, endorsement reports, endorsement certificates, and ranking blocks. The above linked paper and CIP outline the many considerations and risks with such a complex solution and will no doubt evolve and update as further prototyping and simulation eventually arrives at the best design. The first such public simulation was presented by Benjamin Beckmann (IOG Director of Architecture & Infrastructure) at ScotFest but there are now Scaling Monthly Open Meetings. IO are collaborating with Sundae Labs and Well-Typed to validate Ouroboros Leios’s implementation. They regularly publish videos updates to their YouTube channel. 

The exhaustive process will follow the familiar trail of security analysis, peer review, auditing, formalization a precise description of the expected behaviors to clarify the design to engineering, performance testing, prototyping, updates to the ledger…and all this is dependent on progress with other features such as ‘On disk storage of ledger state’, a successful Ouroboros Genesis rollout, increased adoption of light wallets, etc.  

Only then will a hard fork to Leios be possible. As Leios involves significant changes to the protocol, it will also require ratification through an on-chain vote.  It is an ambitious vision, but IOG and the Cardano community are building on granite, reaping the rewards of doing things the right way from the start. All the features and concepts described in this book are anchored in deep academic research, peer-reviewed by the brightest minds in cryptography and implemented based on formal specifications. 

Oct 3, 2022. Re: Input Endorsers, Let’s Talk Basho. CH

So, what happens is that you go from this standard process of a chain of blocks, and there's only one canonical view, to basically, doing a lot of these things asynchronously and in parallel, and they just kind of get batched together, and then asynchronously and in parallel, lots of stuff happens and then they get batched together… So, this concept of input blocks and key blocks, as discussed in our parallel chains paper.

Now this batching…you think of Mithril certificates where you talk about batching transactions, events together …you also could reuse this technology in the extended UTxO model to patch blocks together. So, it gives you a way of figuring out conflict-free history, and potentially what this means is that you have asynchronous parallel processing of an enormous amount of events. So, the throughput gains, assuming new data structures, and assuming new designs, are gargantuan for this because you basically can be real time, continuously running computations. Right now, in the current design, only 0.25% of your block time budget is for computation.
 
So, running execution of scripts… so that's incredibly limiting …0.25%, not 25%, but 0.25% of your block time is for script execution, so it's a very scarce resource. Here it's asynchronous, so it's continuous execution. So, we expect to see not just a 10x, but a very very very significant increase in speed, and a reduction in cost… 



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
[^101]: Ouroboros Family (Input Endorsers), youtu.be/PF1SW7e137A?t=1760
[^102]: Prism: Scaling Bitcoin by 10,000x, arxiv.org/abs/1909.11261
[^103]: Presentation, Prism: Scaling Bitcoin, youtube.com/watch?v=gTJyDtuWvUQ
[^104]: Advances in Ouroboros: Scaling for Future Growth, youtube.com/watch?v=xKv94MwSNBw
[^105]: The longest chain is what individual nodes accept as the valid version of the blockchain. The rule that nodes adopt the longest chain of blocks allows every node on the network to agree on what the blockchain looks like, and therefore agree on the same transaction history. The Longest Chain Rule ensures that the network will recognise the ‘chain with most work’ as the main chain. The chain with the most work is typically (not always) the longest of the forks.
[^106]: Proof-of-Stake Longest Chain Protocols: Security vs Predictability, tselab.stanford.edu/downloads/PoS_LC_SBC2020.pdf
[^107]: Gaži, Kiayias, Russell (2020), 'Tight Consistency Bounds for Bitcoin', eprint.iacr.org/2020/661.pdf
[^108]: Input Endorsers on stack exchange, cardano.stackexchange.com/questions/4626/what-are-input-endorsers-and-how-do-they-make-cardano-more-scalable
[^109]: In telecommunication and radio communication, spread-spectrum techniques are methods by which a signal generated with a particular bandwidth is deliberately spread in the frequency domain, resulting in a signal with a wider bandwidth.
[^110]: Coutts, Panagiotakos, Fitzi (2022), 'Ouroboros Leios: design goals and concepts', iohk.io/en/research/library/papers/ouroboros-leios-design-goals-and-concepts/
[^111]: CIPs/CIP-0079/README.md, github.com/cardano-foundation/CIPs/blob/ouroboros-leios/CIP-0079/README.md
[^112]: CIP-0079? | Implement Ouroboros Leios to increase Cardano throughput, github.com/cardano-foundation/CIPs/pull/379
[^113]:  Driving continued technology advancement through Input Endorsers, youtube.com/watch?v=IGu_1bl6UHQ
[^114]: Let's Talk Basho, youtu.be/fhVo-2QUjLM?t=780
[^115]: Fitzi, Gaži, Kiayias, Russell (2018), 'Parallel Chains: Improving Throughput and Latency of Blockchain Protocols via Parallel Composition', iohk.io/en/research/library/papers/parallel-chains-improving-throughput-and-latency-of-blockchain-protocols-via-parallel-composition

