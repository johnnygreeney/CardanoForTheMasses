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
[^15]:
[^16]:
[^17]:
[^18]:
[^19]:
[^20]:
[^21]:

[^110]:
[^111]:
[^112]:
[^113]:
[^114]: Fitzi, Gaži, Kiayias, Russell (2018), 'Parallel Chains: Improving Throughput and Latency of Blockchain Protocols via Parallel Composition', iohk.io/en/research/library/papers/parallel-chains-improving-throughput-and-latency-of-blockchain-protocols-via-parallel-composition

