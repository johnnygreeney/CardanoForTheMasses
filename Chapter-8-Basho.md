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




**_To be uploaded soon..._**

[^01]: Protocol parameters, cexplorer.io/params
[^02]: Performance engineering: Lies, damned lies and (TPS) benchmarks, youtube.com/watch?v=gpSnyCn2s9U
[^03]: Cardano became the most developed crypto project on GitHub in 2021, cointelegraph.com/news/cardano-became-the-most-developed-crypto-on-github-in-2021-santiment
[^04]: Cardano Surpasses Ethereum In GitHub Daily Development Activity, investing.com/news/cryptocurrency-news/cardano-surpasses-ethereum-in-github-daily-development-activity-2956870
[^05]: Cardano Review 2024, coinbureau.com/review/cardano-review/#cardano-developer-ecosystem
[^06]: Tim Harrison, ‘How we are scaling Cardano in 2022’, iohk.io/en/blog/posts/2022/01/14/how-we-re-scaling-cardano-in-2022/
[^07]: Basho, Input Endorsers, and the Future of Scalability, youtube.com/watch?v=EYc7r5s8cco
[^08]:
[^09]:
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
[^21]:

[^110]:
[^111]:
[^112]:
[^113]:
[^114]: Fitzi, Gaži, Kiayias, Russell (2018), 'Parallel Chains: Improving Throughput and Latency of Blockchain Protocols via Parallel Composition', iohk.io/en/research/library/papers/parallel-chains-improving-throughput-and-latency-of-blockchain-protocols-via-parallel-composition

