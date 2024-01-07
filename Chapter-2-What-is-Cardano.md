# Chapter 2: What is Cardano?

*‘We tell you what we're going to do, we write it down, we go do it, and then we tell you that we did it, and we show you the evidence and proof ... it's the Paul Halmos way of doing things’* ― Charles Hoskinson

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/chapter%202%20tweet.png "Tweet what is cardano")

Cardano is a decentralized, third-generation, proof-of-stake blockchain platform. It is the first blockchain to emerge from a scientific ethos and a research-driven methodology. Ada (₳, or ADA is the ‘ticker’ used on cryptocurrency exchanges) is the first cryptocurrency built on Cardano.  

__December 12, 2020. How do you explain the Cardano project and its mission in a few minutes to someone not engaged in the cryptocurrency space or even the financial sector?__ CH:[^1]

> The easiest way of explaining it is that the world is going through an upgrade, where we will go from a split system to a unified system. Right now, we have two systems, the developed world and developing world system. The developed world system has banks, insurance, credit; it has identity, you can do business online. You can build trust with people, manage risk and be able to grow wealth. So, any person born in a developed world country, if they work hard, has a good chance of getting to a point where they can retire and have a good life. That means a life where they have food, water, shelter, etc. They’re able to pursue things that make them happy and have enough left over that when they become weak and vulnerable, their savings can cover them to pay for those infirmities.
>
>When you look at the developing world, for no fault of their own, they live in systems where wealth creation is very difficult. Even if you have some of it, you can’t insure it and hedge it, so when an event happens, be it a war or natural event like a hurricane or a tsunami, they get wiped out. So, the world is upgrading so that we'll have a unified system where all 7-8 billion people live under one financial operating system. So, your identity is interoperable and universal. You can get a loan no matter who you are or where you are. You can get insurance no matter where you’re at. You can do business with anyone in the world in a friction-free way.
>
>The point of Cardano is to acknowledge this must be done with principles. So, what are we trying to accomplish? We're trying to push power to the edges, and put you in charge of your own money, put you in charge of your own identity, put you in charge of your own voice and give you governance and these types of things. So that when we get to that universal system we get to an open, decentralized, principled system that can’t be co-opted. Highly resilient to people trying to come and tamper with it, and then suddenly the richest people in the world, the Jeff Bezos’s of the world, will use the same system as the poorest people in the world, and both will have a better system than the system that came before it, in both of those old systems. That’s what we’re trying to accomplish.

## Foundational concepts

As discussed in Chapter 1, a blockchain has some features of a database, in this case an accounting ledger,[^2] that is copied and distributed to all users of the blockchain. The blockchain consists of a network of nodes[^3] linked across the internet that store data or valuable digital files in blocks.[^4] Transactions verify these blocks, which are then connected in a chain in chronological order. The details of these transactions are etched forever in the block and cannot be changed.

This blockchain technology, also known as distributed ledger technology (DLT), offers a decentralized and accessible data structure for digital files and documents. Financial payment and transaction data, as well as other sorts of information such as commercial records and information for supply chain management, might be included.

A decentralized blockchain is independent of centralized, controlling companies, institutions, or intermediaries because it keeps data in a decentralized way. This increases the visibility of data storage and administration. A fundamental aspect of blockchain is that records are stored immutably, which means they cannot be modified, falsified, or destroyed without causing the chain of records to be broken.

A blockchain may be likened to a book of permanent records, with each page serving as a data storage device.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/figure2.1blocks.png "blocks")

**Figure 2.1:** Infographic of blockchain blocks linked by hash[^5] pointers

Networks can be configured in several ways (see Figure 2.2):

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/figure2.2threenetworks.png "3 networks")
<br> **Figure 2.2.** Three types of network structures.

With decentralized blockchains, users can deal with each other directly – peer to peer – without having to go through a central, controlling system

-   Centralized systems: in most cases, a single central server manages all data and actions. This raises the possibility of a single point of failure while also implying that the controlling organization (typically a bank or a government agency) makes all the decisions.  
      
-   Decentralized systems: all data and transaction records are encrypted and kept over a network of linked, independent nodes and terminals, rather than on a single server. This assures security, transparency, and independence from centralized institutions.  
  
-   Distributed systems: these depend on several server nodes, each of which serves a portion of the total number of users.  
      
In addition to providing an immutable and secure database, blockchains serve as a functional environment for transmitting cash, creating digital currencies, and processing complicated transactions, including smart contracts (automated digital agreements).  
  
**What is a cryptocurrency?**  
  
A cryptocurrency is a digital asset that is recorded on a ledger and is usually intended to be used as a form of payment for products or services.

In a decentralized setting, blockchain ledgers serve as the foundation technology for cryptocurrencies. To allow the minting (creation) of cryptocurrencies and to safeguard and validate crypto ownership and money movement records, blockchain systems use stringent cryptography methods. A government, or centralized financial institution, has no influence on the protocol level of a cryptocurrency. They can certainly influence price indirectly through rumor, threat (enactment) of legislation. A cryptocurrency’s worth, links to real-world data, market supply and demand are what define it.

When transmitting crypto payments, addresses[^6] are used. Each address is a one-of-a-kind identifier made up of a string of numbers and letters derived from each user’s public keys.

Each blockchain ledger has its own cryptocurrency that provides the ‘oil’ to run the system. This cryptocurrency is ‘native’ to the blockchain because it interacts directly with the blockchain. Cardano’s founding native currency, ada (₳), is the blockchain’s primary payment unit. Ada may be used to pay fees, make deposits, and is the sole currency in which rewards[^7] are given out. This will change with sidechains (discussed later in Chapter 8).

The smallest ada denomination is a lovelace. 1,000,000 lovelaces = 1 ada. Because transactions are calculated to six decimal places, it is easy to divide a single ada into fractions.  
  
**What is a native token?** 
  
Cardano allows users to generate (mint), or delete (burn), their own tokens. These are digital assets, each of which is minted for a particular purpose. On Cardano, tokens are native assets, meaning that they interact directly with the blockchain, rather than being generated using a smart contract. This means that users, developers, and companies may create tokens that reflect a value footprint on the Cardano blockchain (as defined by the community, market state, or self-governed entity). A token may be fungible (replaceable) or non-fungible (unique), and it can be used as a payment unit, a reward, a trade asset, or a holder of information.

## Why is Cardano different?

Cardano is a durable blockchain that is designed to be secure, scalable, and interoperable.[^8] Importantly, Ouroboros, Cardano’s proof-of-stake consensus protocol, has been shown to provide the same security assurances as proof-of-work blockchains such as Bitcoin.

Cardano is described as a ‘third-generation’ blockchain:

-   first generation: Bitcoin, a proof-of-work blockchain;  
-  second generation: Ethereum brought programmable capabilities and smart contracts to blockchain. However, it was flawed because, like Bitcoin, it originally used a proof-of-work system that wasted huge amounts of energy to solve ever-more-complex mathematical puzzles that have no purpose apart from validating transactions. It is also not very scalable, so the more transactions are performed the slower the blockchain becomes, and the more expensive it is to make a transaction. In September 2022, Ethereum finally transitioned from proof of work to proof of stake, but this is only a step on long, convoluted Ethereum 2.0 roadmap. Transaction (gas) fees remain high, and there are unattractive features like slashing[^9]  and uncertainty around users’ stakes being locked up indefinitely.[^10] 
-  third generation: Cardano uses proof of stake, which uses trivial amounts of energy, to provide all the capabilities of Ethereum. It is also designed to grow, work with other blockchains, and has a treasury built in, and a structure for managing change in the future.
    
The engineers who wrote the open-source code for Cardano decided that the best way to produce high assurance software systems that users could trust to handle digital currencies was to employ formal methods such as mathematical specifications, property-based tests, and proofs. Cardano was designed using formal methods to get strong guarantees on the functional correctness of the system’s basic components.

One of Cardano’s central tenets is security. Haskell, a secure functional programming language, is used in its development. A functional language like Haskell promotes the use of pure functions[^11] in system design, resulting in an architecture that is easily tested in isolation. Furthermore, Haskell’s sophisticated capabilities provide powerful ways to ensure the code’s correctness, such as basing the implementation on formal and executable specifications, thorough property-based testing, and simulation testing.

Cardano must be able to grow and interact with traditional finance systems to provide a robust infrastructure on a global scale. Despite the fact that Cardano was built with resource efficiency in mind, scale is still an issue, as it is for all blockchain protocols. To address the problem of growth, IOG researchers developed Hydra,[^12] a protocol that can be run on top of Cardano[^13] and allows transaction and smart contract processing off the main chain. Hydra, and many more scalability solutions are discussed in Chapter 8.

Performance engineering techniques were used to test which design choices helped IOG achieve resilience, performance, and scalability. Another important goal of Cardano’s architecture is to prevent centralization by using economic incentives that encourage decentralization. Stake pools[^14] have an economic incentive to expand as soon as they are created, so it was critical to make it less appealing for a stake pool to become too large. However, a balance has to be struck because a limited number of big pools is more cost-effective than a large number of tiny pools.

A balance was accomplished by altering the reward formula. In a basic system, a pool’s total rewards are simply proportional to its stake, hence the larger the stake, the better. With Cardano, if a pool collects more stake than a given threshold (1/k, where k is an adjustable parameter), the pool’s payout will no longer rise. The pool is said to be saturated,[^15] and delegating more ada stake will not increase the rewards. The result is k pools of nearly equal size if everyone acts in their own self-interest to maximize their rewards.

Interoperability, or the capacity to communicate with other systems, is a fundamental architectural component of Cardano. The use of sidechains is one of Cardano’s innovations. The design means that the system can be compartmentalized, and it enables interoperability inside the blockchain platform. A sidechain holds and manipulates data off the main chain. Many sidechains may function at the same time, and if one fails, the rest of the system remains operational. As a consequence, the blockchain has more certainty and trustworthiness. Assets can be moved between separate blockchains that run under distinct rules, procedures, or languages, as well as various methods of accessing the network, by using sidechains.

Cardano’s architecture also prioritizes governance[^16] to maintain the system’s long-term viability and flexibility. A well-developed governance structure allows Cardano’s long-term development to be funded effectively and democratically. Cardano’s treasury system is a long-term financing source for the protocol and projects building on it. It will be run by the community and will allow for a decentralized, collaborative decision-making mechanism to ensure Cardano’s continued growth and upkeep. Various financing sources can be used to top up the treasury, such as the aggregation of newly minted coins, a portion of stake pool rewards, transaction fees, and donations. It will be able to support project development and pay for improvement recommendations using the funds earned. Additionally, Cardano improvement proposals (CIPs) are issued to stimulate and codify community conversations about new features and their development.

A voting system is at the heart of the treasury, allowing ada holders to decide on funding proposals and determine how funds are spent. This will guarantee that choices are taken democratically rather than by a small group of people. This voting method will decide on choices such as financing projects, allowing protocol upgrades, and implementing any constitutional changes such as decision-making process modifications. Project Catalyst[^17] is evolving into a fully on-chain democratic governance mechanism that will enable the project to expand over time while also allowing it to support itself in a sustainable manner through a visionary treasury system.
 
**20 January, 2021. What is Project Catalyst? How can people get involved for future funds?** CH:[^18]

>So, we’re building a whole stack of voting into Cardano and we’re partnered with a lot of great companies and think tanks. For example, we’re partnered with an innovation management company called IdeaScale… they’ve been around for almost a decade. They work with Pfizer and Boeing … so, yes, how’d Pfizer come up with that vaccine so quickly? They use IdeaScale. So, we basically brought them in along with some decentralized tooling and we created a whole new voting system. We spent four years researching how to do a private blockchain-based voting system out of Lancaster University that can scale to lots of users.
> 
> Basically, what we’ve been doing is systematically launching funds… so the treasury of Cardano takes some of the inflation that normally you’d give to stake pool operators or miners… and it gives it to a decentralized account and then people submit ballots to get funded. Over time, people can vet those ballots and it goes through a process, like a gauntlet… and if they survive, they can vote… and if enough votes come in you get funded.

**Cardano differentiators**  
  
The following aspects of Cardano are outlined in detail in later chapters, but here is a summary of the blockchain’s innovations.

**Academic research**: formal methods, including mathematical specifications, property-based tests, and proofs, are the most effective means of delivering high-assurance software systems. They also provide users with trust in the management of digital assets. Cardano was created with formal methods to obtain strong assurances on the functional correctness of the system’s key components. The research that supports Cardano is published at academic conferences and in journals, papers are available to the public and all Cardano development activity is documented in weekly updates every Friday.[^19]

Only when the Ouroboros consensus algorithm had been proven to be mathematically secure by an academic team led by Prof Aggelos Kiayias at the University of Edinburgh did the software engineering work begin on implementing the blockchain in code. IOG are rightly proud of their growing presence in academia around the globe.[^20] The significance of these partnerships and investments will come up again later in Chapter 9 (Voltaire).

**System design**: Cardano is built in Haskell, a secure functional programming[^21] language that facilitates the creation of systems using pure functions, resulting in a design that is easy to test in isolation. Furthermore, Haskell’s sophisticated capabilities include powerful ways to ensure the code’s correctness, such as basing the implementation on formal and executable specifications, thorough property-based testing, and simulation testing.  
  
**Security**: Ouroboros[^22] (Cardano’s proof-of-stake protocol) offers strict security assurances; it is based on peer-reviewed papers presented at top-tier cybersecurity and cryptography conferences and publications. Only around half of the users who are active in the network are required to follow the protocol; in fact, momentary rises beyond the 50% threshold can be accepted. As a result, Ouroboros is much more robust and adaptive than traditional Byzantine fault tolerance (BFT) protocols,[^23] which must forecast the degree of expected involvement and may shut down if the prediction is incorrect.

Cardano’s network protocol uses a pull communication method. If a node tries to push information, it is automatically disconnected.  
  
-   Unique built-in security capabilities:
	- VRF (verifiable-random function): used to prove that a node has the right to create a block in a given slot.[^24]
	- VRF[^25] use makes the consensus difficult to attack because it’s impossible to predict the next producing nodes.
	- KES (key-evolving signature): keys are rotated after a certain number of epochs.[^26]
    
-   Plutus, Cardano’s native scripting language,[^27] uses a formal methodology to bring advanced smart contract capabilities to the blockchain without compromising security.
-   dApp[^28] certification program to be rolled out in 2023.
    
As is best practice, IOG rotates between various security auditors such as Bcryptic, R9B (root9b), Grimm, rpisec and Kudelski. The reports are available on the IOG GitHub page.[^29]

**February 4, 2020. Re: security.** CH:[^30]

>So, when we started the Cardano project we said, ‘well let's write software differently and let's think about science a little differently than how our industry thinks about it …as opposed to writing some white paper or just writing ideas down or saying here's the code, enjoy it’. We said we will start with the peer-reviewed scientific process. So, the first thing we did is that we hired a large group of scientists, and we asked a lot of hard questions, and they thought deeply about security proofs, adversaries and security models and deeply about what had been done and where original innovation needed to exist.
> 
> Now that alone, at the time, was a major step forward because it had not simply been done at a large commercial scale by anyone in our industry. Now we're starting to see that with David Chaum and Silvio Micali entering the space, and others actually hiring real scientists, writing real papers, including Ethereum, that that's no longer a core distinction, but we didn't stop there.
> 
> In 2015, we also aspired to have this concept of formal methods, and this is something that very few software engineers in our space fully understand or appreciate the value of. So basically, what a formal methodology is, it's where you say, ‘okay let's write down in a very specific, detailed, rigorous, mathematical way what we intend on doing …what is what’.
> 
> So, we have this concept of Ouroboros, there's many flavors of it, but what does it actually mean to go from these dry, dead papers that our academics have written to something that an engineer can look at, and know with absolutely no ambiguity, that what they have created matches the intent of the authors of the system? So basically, you have to write a specification for this, and specifications can then be analyzed in a rigorous way for correctness. You can use all kinds of techniques like model checking and SAT solving[^31] and so forth to verify that your specification meets some sort of collection of design requirements or tests.
> 
> So, we chose to go down this road and unfortunately most of the time, when you write software in this way, it adds years to your roadmap and that's exactly what happened with us. When we went down this road we had to hire, in addition to a bunch of scientists, a bunch of formal methods experts and then we had to figure out how to do formal methods with cryptocurrencies. At the time, no one had actually done that before.

**Power consumption**: Cardano is a proof-of-stake blockchain. It requires far less power to operate than proof-of-work chains. The Bitcoin network grows by computers doing energy-intensive calculations – a process known as proof of work – which is unsustainable in the long run. According to the Cambridge Bitcoin Electricity Consumption Index,[^32] the machines that run Bitcoin use as much energy each year as a country such as Norway or Sweden. Ouroboros identifies the participants’ leverage in the system using stake as the primary resource. Despite ‘costless simulation’ and ‘nothing at stake’ attacks,[^33] which were previously regarded to be fundamental hurdles to stake-based ledgers, no physical resource is spent in the process of ledger maintenance. This distinguishes Ouroboros from proof-of-work methods, which need exorbitant energy consumption to establish consensus.

**Seamless upgrades**: in older blockchains, upgrades were done via hard forks. When a hard fork occurs, the existing protocol is disabled, new rules and modifications are introduced, and the chain is restarted – with all the history destroyed. Hard forks are handled differently by Cardano. Rather than making drastic changes, the Cardano hard fork combinator[^34] (HFC) allows for a seamless transition to a new protocol while preserving the history of blocks and causing minimal inconvenience to users.

**Decentralization**: Cardano is managed via a community-run network of over 3,000 distributed stake pools. Without relying on a centralized authority, network members verify all blocks and transactions.

Ouroboros includes a reward-sharing system to encourage participants to form operational nodes, known as stake pools, that can provide quality service regardless of how stake is divided among the user population. As a result, all stakeholders contribute to the system’s operation, guaranteeing resilience and democratic representation, while the expense of ledger maintenance is dispersed effectively across the user community. The system’s features discourage centralization. As a result, Ouroboros is inherently more inclusive and decentralized than other protocols, which either end up with a small number of actors accountable for ledger maintenance or give no incentives for stakeholders to join and deliver quality service.

​​Ouroboros also provides a better staking[^35] experience. Cardano doesn't impose penalties such as stake slashing or lock-up (bonding). When you delegate ada to a stake pool from your wallet, it isn’t locked up. Rewards are distributed every epoch (about 4% of the ada in circulation) and you can access or withdraw the stake at any time. Plus, staking on Cardano is non-custodial which means there’s no risk of slashing either. As a delegator, your staked funds are never at risk of being taken by the stake pool.  

-   The Ouroboros protocol is highly efficient meaning that stake pool operators can run their nodes on low spec hardware, with less hardware investment required than other blockchains.  
      
-   Over 80% of tokens are held by the public and more than 70% of ada is staked in millions of wallets.
    
Websites such as AdaPools (adapools.org) and PoolTool (pooltool.io) give information about stake pools.  
  
A **functional environment** for business: Cardano is laying the groundwork for global, decentralized finance by allowing developers to create decentralized applications (dApps) that run on functional and domain-specific smart contracts and provide multi-asset[^36] tokens for any need. Two smart contract language platforms are provided: Plutus,[^37] which is ‘Turing complete’,[^38] so can be used for any purpose; and Marlowe, a specialized language for banking and financial services.

Cardano adds programmability to Bitcoin’s proven UTXO model[^39] with its extended UTXO (eUTXO) ledger model, offering smart contracts with increased scalability, while maintaining security. With eUTXO, metadata[^40] and scripts are bundled together in a single transaction for greater throughput. Transaction verification is simpler, so you can predict what’s going to happen, including how much a transaction will cost. And if a transaction fails, no fee is charged. The testing features provided in Plutus and Marlowe mean that developers can ensure their smart contract scripts operate as intended.

Fungible and non-fungible tokens (NFTs) are treated as native tokens, so no smart contracts are needed. This reduces complexity, making it easier for developers, and opens up new uses – and a superior gaming and metaverse experience.

## Why choose Cardano?

Of the  18,000  cryptocurrencies[^41] around today, trying to grasp what differentiates one from another can be overwhelming. Are cryptos actually ranked on their merits? How is something as trite as Doge[^42] in the top 20 while a technical marvel like Ergo[^43] languishes outside the top 200? If you look at it long enough, CoinMartketCap begins to look like the odds for a horse race, and just as unpredictable.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/figure2.3coincap.png "Horse vs coincap")

**Figure 2.3.** Horse racing odds vs Coincap.io

So what is so special about Cardano? The first generation of blockchains (Bitcoin) provided safe cryptocurrency transmission via decentralized ledgers. However, such blockchains did not offer a suitable environment for the settlement of complicated transactions or the creation of decentralized applications (dApps). The second generation of blockchain technology (Ethereum) brought more advanced solutions for writing and executing smart contracts, application development, and the creation of tokens as blockchain technology evolved. However, second-generation blockchains were also built using energy-hungry proof-of-work mining and face scalability challenges.

Cardano is regarded as a ‘third generation’ blockchain platform because it incorporates the characteristics of previous generations but avoids their pitfalls and can adapt to meet all user demands. It is built on Ouroboros, a peer-reviewed[^44] proof-of-stake blockchain protocol that was published at the world’s top cryptology research conference (the International Association for Cryptologic Research 37th International Cryptology Conference – Crypto 2017). 

The Cardano papers are open-access, patent-free, and give all the technical information necessary for anybody with the appropriate technical skills to verify the accuracy of the performance, security, and functionality claims (iohk.io/research). Other projects have borrowed heavily from IOG’s research, for example, Polkadot’s hybrid consensus protocol was inspired by Ouroboros.[^45]  You can inspect the citations on Google Scholar: a search produces about 1,800+ citations.[^46] Similarly, the ‘Bitcoin backbone protocol’ (GKL) paper, which has been the foundation for much of Cardano has more than 18,000 citations.[^47]

The ideal solution should offer the greatest levels of security, scalability (transaction speed, data scale, network capacity), and functionality to handle all aspects of business deal settlement, not just transaction processing. Furthermore, it is critical to guarantee that blockchain technology continues to evolve in terms of sustainability and interoperability with other blockchains and financial institutions.

To meet these demands, Cardano focuses on principles such as:

**Scalability**: assures that the Cardano ledger can handle a huge number of transactions without slowing down the network. Higher bandwidth possibilities are also provided through scalability, allowing transactions to transport a sizable quantity of supporting data that can be handled simply inside the network. IOG is gradually introducing Hydra along with other solutions such as sidechains. dcSpark (third party development company) launched the first sidechain, Milkomeda and IOG will launch their own soon. (More on this later in Chapter 8).

**Interoperability**: guarantees a multi-functional environment for financial, business, or commercial processes by allowing users to engage with numerous currencies across multiple blockchains. Interoperability with centralized financial bodies is also critical for ensuring legitimacy and ease of use. 

**Sustainability**: building a proof-of-stake blockchain necessitates ensuring that the system is self-sufficient. Cardano is designed to enable the community to sustain its development by engaging in, submitting proposals, and implementing system innovations to promote growth and maturity in a fully decentralized way. To maintain long-term viability, the community controls the treasury system, which is regularly supplied from various sources such as freshly minted coins held back as financing, a portion of stake pool rewards, and transaction fees.

## Cardano roadmap
Cardano’s development roadmap[^48] has been divided into five eras, each focusing on a different feature set:

 - Byron focused on establishing a foundation.  
- Shelley focused on network decentralization.  
- Goguen is all about smart contracts.
- Basho is the drive to attain true scalability.  
- Voltaire is based on implementing decentralized governance.

Each era is built around a collection of features that are implemented and improved over many code releases. While the work for each of these development streams is delivered in order, it is typically done simultaneously, with research, prototyping, and development happening at the same time throughout. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/roadmap.png "roadmap")

**Figure 2.4.** from roadmap.cardano.org

**Byron**

Byron laid the groundwork for the creation of Cardano. It enabled users to purchase and trade ada on a proof-of-stake blockchain network. Initially, the Cardano ledger was set up as a federated network, with stake pools run by Input Output Global and Emurgo handling block generation and transaction validation. Byron saw the release of the Daedalus and Yoroi wallets,[^49] as well as a block explorer for examining the blockchain.[^50] 

**Shelley**

The Shelley development era offered a decentralized ledger, resulting in a new economic structure that propels network growth and optimization. In the run-up to decentralization, an Incentivized Testnet (ITN) was set up to demonstrate that Cardano would be viable in the long term with only community-managed pools. 

Shelley emerged from Byron’s federated network, with the dispersed stake pool operator (SPO) community producing an increasing number of blocks until the network was fully decentralized in 2021. In terms of stake pool operation, delegation[^51] preferences, and incentives, Shelley focuses on essential processes that provide an improved user experience. 

**Goguen**

The development of Goguen focuses on the creation of a worldwide, financial, and multi-functional system for the creation of decentralized applications (dApps), smart contract support, and custom token issuing. 
Goguen is a fundamental component in establishing a flexible platform for developing applications in areas such as supply chain, track and trace, finance, medical records, identity voting, property registration, and peer-to-peer payments.

**Basho**

Basho concentrates on Cardano’s optimization in terms of network scalability and interoperability. While past rounds of development concentrated on decentralization and new features, Basho is all about enhancing the Cardano network’s fundamental performance to facilitate growth and uptake for busy applications.

**Voltaire**

Voltaire is built on decentralized governance and decision-making, allowing the Cardano community to vote on network development updates, technological advancements, and project finance. To be truly decentralized, the Cardano network needs not just the distributed architecture developed during Shelley, but also the capacity to be maintained and enhanced in a decentralized manner over time. Project Catalyst is about putting the mechanisms in place so people can apply for funding and vote on proposals.

## How does Cardano work?

The Cardano node is the network’s top-level component that powers the blockchain. The networking layer, which is the driving force for supplying information exchange needs, connects network nodes to one another. For enhanced data flow, this provides new block diffusion and transaction metadata. Cardano nodes keep in touch with each other using a peer-selection method. You participate in and contribute to the Cardano network by hosting a node. As with every aspect of Cardano, security is paramount. The network protocol uses a pull communication method so if a node tries to push information, it is automatically disconnected.

Stake pools are responsible for transaction processing and block generation and use the Cardano node to check how the pool interacts with the network. They operate as secure server nodes, storing and maintaining the pooled stakes of several stakeholders in a single entity.

**Block production** 
The purpose of blockchain technology is to create a cryptographically connected, independently verifiable chain of records (blocks). A network of block producers collaborates to enhance the blockchain as a whole. A consensus protocol ensures that the chain is transparent and determines which candidate blocks should be chosen to expand it.
Valid transactions that have been submitted may be included in any new block. A block’s producer signs it cryptographically and links it to the preceding block in the chain. This makes it hard to erase transactions from a block, change the order of the blocks, remove a block from the chain (if it has a lot of other blocks following it), or add a new block to the chain without notifying all network members. This protects the blockchain expansion’s integrity and accountability. 

**Slots and epochs**
The Ouroboros protocol is used by the Cardano blockchain to support chain consensus. Time is divided into epochs. An epoch is made up of slots, each of which lasts one second. There are currently 432,000 slots (five days) in a Cardano epoch. Slot leaders[^52] are elected randomly from among the stake pools. One node should be nominated every 20 seconds on average, for a total of 21,600 nominations every epoch. One of the randomly drawn slot leaders will be added to the chain if they create blocks. A node that goes offline will miss its chance, and another node will be chosen. This means stake pools have to be very reliable and be online all the time. The remainder of the candidate blocks will be discarded.
There are several versions of Ouroboros: Classic, Byzantine Fault Tolerance (BFT), Genesis, Praos, and Leois. More about this in Chapter 3.

**Slot leader election**
The Cardano network is made up of a number of stake pools, or delegators, that govern the aggregated stake of their owners and other stakeholders. The slot leaders are chosen at random from the stake pools. The bigger a pool’s stake, the more likely it is to be chosen as a slot leader and generate a new block that is accepted into the blockchain. This is the foundation of Cardano’s proof-of-stake (PoS) approach. Cardano includes an incentive scheme that discourages delegation to pools that already control too much of the overall stake, to preserve a level playing field and avoid a small number of extremely large pools controlling most of the stake.

**Transaction validation**
A slot leader must confirm that the sender has included enough resources to pay for the transaction and that the transaction’s requirements are satisfied while validating a transaction. The slot leader will record the transaction as part of a new block, which will subsequently be joined to other blocks in the chain, if it fits all these conditions.

**How to purchase ada?** 

Most people buy ada via centralized exchanges such as Kraken, Coinbase or Binance. The steps are documented in Cardano Docs and via a plethora of blogs and YouTube videos.[^53] Centralized exchanges are no longer the only fiat onramps available with wallets such as eternl and vendors like nmkr.io offering the user the ability to buy Ada with their local currency.

**How to Delegate and earn rewards**

The number of ada you hold determines the size of your stake. Cardano users may receive passive rewards for verifying blocks if they have a stake in the protocol. 

Because not everyone has the time, skills, or money to operate a stake pool, ada holders may delegate their stake to a chosen pool and have it managed on their behalf by an operator. This enables everyone to contribute to the consensus and receive rewards without having to keep a node online all of the time. The bigger the stake in a pool, the greater the rewards for its owners. You can spend your ada whenever you choose, regardless of whether it has been delegated.

Ada holders initially relied on the *Daedalus* wallet from IOG (full node, desktop wallet) or Yoroi from Emurgo (light, mobile client) to delegate their share. But as Cardano matures, there are now many more options. In June 2022, IOG announced a new light wallet, *Lace* will be one-stop shop for everything in the Cardano ecosystem. Meanwhile dcSpark’s (dcSpark.io) Flint and eternl are just two of the many wallets available.[^54] Here are a few guides recommended in Cardano Docs:

- How to choose a stake pool[^55]
- How safe is it to delegate to a stake pool?[^56]
- How to delegate to a stake pool (Daedalus)[^57]
- Staking and delegating for beginners (Daedalus)[^58]
- How to delegate from the Yoroi wallet[^59]

Cardano-node, originally developed by IOG, is now an open-source project in its own right. IOG are placing more and more of an emphasis on their open-source credentials. You can review the repository on GitHub[^60] to understand how you can contribute, codes of conduct, benchmarking results, etc. and visit CardanoUpdates.com for roadmap details.

## Cardano design decisions

Many people discovered Cardano by watching Charles Hoskinson’s Whiteboard YouTube presentation.[^61] However, Cardano didn’t start out with a detailed plan or even a white paper, as many open-source initiatives do. IOG explored the cryptocurrency landscape by adopting a ‘first principles’ approach.[^62] The Scorex project[^63] and IOG’s vault of research papers[^64] were the product of this study. 

Unlike successful protocols such as TCP/IP,[^65] most cryptocurrencies have no layering in their architecture. Regardless of whether it makes sense, there has been a desire to retain a single concept of agreement around facts and occurrences recorded in a single ledger.

For example, Ethereum has accumulated vast complexity in its quest to become a world computer, yet it is plagued by minor issues that might jeopardize the system’s capacity to function. Should every dApp, regardless of its economic worth, maintenance costs, or regulatory implications, be treated as a first-class citizen?

**Layered architecture**

The focus of IOG’s design is to accommodate the social features of cryptocurrencies, to create layers by separating value accounting from computation, and to answer the demands of regulators while adhering to the founding principles.[^66] IOG also assessed protocols via peer review and inspected code against formal specifications[^67] whenever possible.

**February 8, 2019, Charles Hoskinson: In Defense of Peer Review**[^68] 

>…unlike journals, which sometimes take years for research to actually get published, fully peer-reviewed and get through the system, conferences are very frequent. If you look at the cryptographic world you have Eurocrypt, CCS, Real World Crypto and dozens of other conferences every year. Almost every month there’s some form of conference going on. So it doesn’t slow you down to write a paper, in a very structured, thoughtful way, get it into a conference and then get some review from the community. Suddenly, now you have some of the brightest people in the world waking up trying to destroy your argument, because they know that it benefits their academic career if they can find a flaw in your paper.

Cardano is a cryptocurrency that acknowledges that ‘money is social’. A social construct is something that comes through human interaction rather than objective reality. It exists because people acknowledge and believe in it. Countries and currencies are two examples of social constructs.

Flexibility and the capacity to handle complexity in any transaction are critical. If the Cardano project is successful in scaling up to be used by billions of people, massive computing, storage, and network resources will be required to handle billions of concurrent transactions. Cardano’s architecture inherits the notion of separation of concerns[^69] from TCP/IP.

Blockchains are, at their core, databases that arrange facts and events based on timestamps and immutability to record asset ownership. It’s non-trivial then to add complicated computation for storing and executing dApps. Do we need to know how much money someone is sending? Do we want to become engaged in deciphering the transaction’s whole narrative?

To figure out what’s happening, a single protocol must be able to comprehend arbitrary events, script arbitrary transactions, allow for fraud arbitration, and even reverse transactions when new information becomes available.

Then there’s the issue of deciding what information to retain for each transaction, which is a challenging design choice. What components of a transaction narrative are relevant? Are they going to be significant in the future? When will it be safe to discard certain data? Is it illegal in certain jurisdictions to do so? Certain computations are by their very nature secret.[^70] It’s always good to remember the difference between confidentiality and privacy.

Privacy and confidentiality are two separate concepts that protect different types of data. 'Privacy' is used in relation to data that is protected by law, whereas 'confidentiality' refers to different data contained in valid contracts and agreements.

A transaction consists of two parts: the mechanism for sending and recording token flows, as well as the reasons and circumstances for transferring tokens. The latter may be very complicated, including gigabytes of data, signatures, and the occurrence of unforeseen scenarios. With a single signature moving value to another address, it can also be straightforward.

Modeling the motives and circumstances of value movement is difficult because they are personal to the parties involved in the most unanticipated ways. Contract law creates an even more complex picture, in which the actors may not even be aware that the transaction does not match commercial reality.[^71] This concept is known as the ‘semantic gap’.[^72]

The general lack of legal clarity around protocol participants’ legal safeguards is another gray area. There is no limit to what a sophisticated cryptocurrency may do. A blockchain such as Cardano can unwittingly facilitate all sorts of crime and malfeasance. Just how complex this is in practice is discussed in various academic papers, including *The Ring of Gyges:[^73] using smart contracts for crime*. 

Cardano and Bitcoin have an advantage in that they have opted to split into layers. Bitcoin gave us Rootstock (rsk.co),[^74] while the Cardano Computation Layer is Cardano’s proposal.

​​IOG provides a reference library of Plutus code for application developers to use in their projects, similar to the Solidity-based[^75] Zeppelin project.[^76] IOG also created a set of tools for formal verification based on the Liquid Haskell project.[^77] 

The ‘Why Cardano’ essay from 2017 describes the vision[^78] for The Cardano Settlement Layer (CSL) vs Cardano Computation Layer (CCL). The same functionality exists today, but it is implemented differently than outlined back then. The layered approach was kept but computation is done on the main chain, Layer 1. This was implemented very carefully as the development of Plutus relied on formal methods and a secure design that would not endanger ‘simple' non-script assets on the chain. The strategy and terminology was revised slightly again in 2023, but don’t worry about that for now, we will revisit this in Chapter 8.

The code base was totally rewritten in a modular[^79] format in preparation for the implementation of the hard fork combinator (HFC)[^80] in March 2020. The modular approach made it far easier to make changes with the HFC. The ‘Byron reboot’ and HFC in 2020, with the move to Ouroboros Praos, were fundamental in implementing code that would support the future of the blockchain. This was a watershed moment in the efficiency of the chain and for the productivity of IOG. It made possible the move to the quarterly update schedule in place today. Nobody had done anything like the HFC before; it made upgrades easy, another advantage of the third-generation approach.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/hfc.png "hfc")

Figure 2.5: Mainnet Byron to Shelley Roadmap

Charles Hoskinson has explained the layered approach in many of his YouTube AMAs (ask-me-anything). Excerpts from some of these are included below for clarity.

**April 21, 2019. Is Cardano going to be more of a sidechain host model?** CH:[^81]

>Cardano has always been a two-layer system, so this concept of the settlement system and a control layer idea …so the control layers are either permissioned or permissionless[^82] and they can have arbitrary complexity. The settlement system has basically everything that you would need for a long-term cryptocurrency …so basically Cardano, at the settlement layer, is kind of like what I would like Bitcoin to look like. […]
>
>In terms of the conceptual design and actually the formal specification, we have a total understanding of what ledgers need to look like, the accounting systems behind them… we have an incredibly intricate understanding of what consensus looks like and the tradeoffs of consensus. We have a detailed understanding of interoperability; we understand how to extend the UTXO model to include pretty much as much scripting as you want… but do this in a very safe way where you have predictable gas cost 

**July 9, 2020. Thoughts on Cross Chain Communication, Sidechains, NiPoPoWs and Litecoin**[^83]

>You can have a maximalist model …and if they (Bitcoin) ever actually implemented this technology, it actually would be competitive. They've had since 2014 to do it but they haven't done it. This is this concept of primary - secondary chains. Used to be called master – slave, but that language is rapidly falling out of use even in different context. Basically, we did this in our original white paper, we said SL (settlement layer) and the CL (computation layer) concept… so the idea is that there's one primary chain and that's where the token lives, ADA. Then that token ADA can be used to power different chains, that have different network logic, it has different consensus rules, it has different ledger rules, a different computational model and somehow these chains don't have their own native token …rather they are at the service of the primary chain. So, let's look at this in the context of the ITN (incentivized testnet).
>
>So let's say that we modify Ouroboros….and Ouroboros now when you're a stake pool operator, instead of just getting one block, you get block Cardano… but then you'd also get block CL1, block CL2… block CLn… and so if you’re a stake pool operator, when your job comes up to expand the state of the chain, you'll actually do that for each of these networks in addition to SL. So you'll generate the normal Cardano block, like all the stake pool operators do, but then you'll make the block for the next network, the block for the next network … and you'll look up that network logic and those consensus rules and the ledger logic and you'll follow the computational model, and these will all be different.
>
>[...] This was kind of an envisioned model that came out of Blockstream[^84] when they were talking about sidechains. They said Bitcoin can be that version of SL, and it could be very simple and safe and secure, and then you could have Ethereum as a sidechain of Bitcoin, send your Bitcoin into that sidechain, operate and then send your Bitcoin back when you're done.

**December 30, 2020. Is the distinction between the Cardano computation layer and the Cardano's settlement layer still relevant?** CH:[^85]

>Yes, and in fact the sidechains that we're going to run are examples of what I call the computation layer. The difference is they're not ephemeral, they're actually permanently there …but yeah that's exactly what we intended.  You have a very stable secure settlement system which is the primary network with the stake pool operators …and you have this collection of sidechains which do different things and have different computational models than the main chain. 

**Regulatory landscape**

If a financial system grows and achieves adoption, it develops a need for regulation, or at the very least a desire for it. Regulatory reform is usually the consequence of periodic market breakdowns caused by the incompetence of some actor(s).

The Knickerbocker Crisis of 1907, for example, led to the establishment of the Federal Reserve System as a lender of last resort in 1913. Another example is the excesses of the United States in the 1920s, which ended in the Great Depression, a devastating financial catastrophe. The Securities Exchange Commission was established in 1934 as a result of this collapse in an attempt to avoid a repeat of the incident or at the very least hold unscrupulous actors responsible. The Bitcoin Genesis block referred to ‘Chancellor on the Brink of Second Bailout for Banks’[^86] implying some inspiration from the events of the time.

One might question the need, breadth, and usefulness of regulation, but one cannot deny that it exists and that major governments have implemented it with enthusiasm, with many subsequently performing an about-turn once they realize the consequences.[^87] Cardano, like other financial systems, must have a viewpoint on what is fair and acceptable in its design. Cardano opted to distinguish between individual rights and market rights.

Individuals should always have complete control over their finances, free of coercion or civil asset forfeiture. This principle must be enforced because, as crises like Venezuela, Zimbabwe and Cyprus have shown previously, and the ongoing war in Ukraine shows today, not all governments can be trusted not to misuse their sovereign authority for the personal enrichment of corrupt leaders. Cryptocurrencies must be designed with the lowest common denominator in mind.

There should never be any tampering with history. Immutability is promised by blockchains. Introducing the ability to rewrite history or the official record offers much too much temptation to change the past to favor a certain actor(s).

There should be no restrictions on the movement of wealth. Human rights are harmed by capital restrictions and other artificial barriers. Aside from the impossibility of enforcing them in a global market where many residents in developing countries migrate outside of their jurisdiction in search of a livable income, limiting capital flows also frequently harms the world’s poorest.

According to these concepts, markets are separate from people. While Cardano believes in individual rights, markets also have the right to publicly express their terms and conditions. If a person decides to conduct business inside this market, they must be held to those T&Cs for the sake of the system’s integrity.  

**December 30, 2020. Is the SEC (Securities & Exchange Commission) the enemy of Crypto?** CH:[^88]

>No…the regulators are not the enemy of crypto … let’s be honest here our space created Bitconnect,[^89] OneCoin,[^90] Mount Gox,[^91] Bitmex[^92]… thousands of scams that have hurt people. Regulators are like vampires, in a good way. They come in when you invite them. Okay, a vampire standing at the door says, ‘can I come in?’ …what brings a regulator into an industry? Happy well-functioned industries where everything is going right? … like how many regulators are there for mathematics? Is there a mathematics exchange commission? …that sits down and says ‘we really need to look into those topologists? …. they’re slippery people, we are deeply concerned about statistics. Yeah, there’s some problems there man, serious problems, 64% of people know that…’
>
>No! because it’s like… what scandals occur in the mathematical world? Occasionally we have an older fields medalist who claims he proved the Riemann hypothesis and turns out his brain’s baked and it is a garbage paper! Okay we’re pretty good at self-regulating in that industry. On the other hand, why is the pharmaceutical industry regulated? Because they make stuff that you put into people’s bodies, and if they that up they break your penis, they break your brain, they break your eyes, you go deaf …. okay more than one person has gone deaf from the first reaction to an antibiotic. There are all kinds of bad things that can occur …so you need to regulate it! Because there are perverse incentives against your health!
…
So let’s look at crypto, you have the ICO (Initial Coin Offering) boom, you have tons of scandals and scams, you have rampant insider trading, you have wash trading on exchanges, you have exchanges failing and the principals of the exchange are stealing the money and fleeing abroad, you have software flaws that were made on purpose to steal people’s money, you have massive misrepresentations… you have impersonations… you have people claiming they’re using project capital for something but they’re actually using to buy yachts and Miami houses and prostitutes and… rah-rah-rah
>
>That is a big neon sign at the front of your door…. ‘Vampire come in!’ …our industry did that, we didn’t self-regulate, we didn’t stop the agency failures, we created a neon sign and welcomed a vampire and now they’re here! …and we’re going to complain that they’re doing stuff… filing lawsuits, getting involved like a bull in a China shop… of course they are, and their ability to act is proportional to the sophistication of the tools and the modernity of the laws. The Howey test[^93] is an artifact of the 1940s …it cannot work in ‘stem cell’ finance, where an asset can be everything… it can be a currency, a commodity and a security all at the same time, could be everything and nothing… 

In June 2022, Charles Hoskinson spoke[^94] before Congress on the ‘The Future of Digital Asset Regulation’. He didn’t focus attention on Cardano, and instead spoke for the industry. The main message he delivered to representatives was cryptocurrencies, in general, should be treated as financial stem cells rather than be rigidly defined as a security, currency or a commodity. Future legislation should be based on principles, not focused on individual jurisdictions or bodies. His contribution was broadly well received.[^95]

**Cardano Vision**

Cardano is a long-term project that has benefited from the input of hundreds of the world’s brightest minds, both within and outside the cryptocurrency sector. It entails constant iteration, active peer review, and leverages the findings of open-source research. 

While no project can meet all goals or please all users, IOG intends to present a vision for what a self-evolving financial stack should look like for countries that don’t have one. Realistically, cryptocurrencies will not replace current financial institutions. Legacy financial systems have always been able to absorb change. Instead, it’s more fruitful to focus on jurisdictions where deploying the old banking system is just too costly, where many people survive on less than a few dollars a day, have no fixed identification, and credit is difficult to come by.

The ability to combine a payment system, property rights, identification, credit, and risk protection into a single mobile app is not just beneficial, but life-altering in these regions. IOG believes Cardano can build on the successes of projects like M-pesa[^96] and Kiva.[^97] If Cardano can transform the way cryptocurrencies are conceived, developed, and financed, then we are heading towards Dr Pangloss’s ‘best of all possible worlds.’[^98]

## Behind the names

**Why is it called Cardano?** CH explains:[^99]

>Girolamo Cardano was the ultimate Renaissance guy, he was a doctor, a lawyer, he was a mathematician, he was a gambler, a complete scoundrel. He was the personal physician of the Pope but then excommunicated but still hung out with the Pope even after being excommunicated, because the Pope liked him. He nearly killed one of his sons in a sword duel because they were sleeping with the same woman. Then he was also a gambler, and he invented a lot of probability theory just so he could be a better gambler. So, he created all this advanced mathematics just so he could count cards and roll dice properly and so forth. And he had a habit of getting kicked out of cities… And he also was a cryptographer because in Renaissance Italy, they had a lot of intrigue between the banking families. So, he invented this wheel device to encrypt messages, so they kept secret communication between the families. So, I just read about him years ago and thought he’s one of the most interesting people I’ve ever read about in my life. So, I was thinking of a cryptocurrency, it could do both good things and bad things, and it also does a little bit of everything and it’s just all-around an interesting system, and I thought it’d be cool to name it after Cardano.
>
>He was just one of those guys that lived a life that was unbelievably rich, wasn’t nice, wasn't evil, he was somewhere in between. He basically built out modern probability theory because he wanted to be a better gambler. He also inadvertently created the Italian peer review process because, at the time, he was around most of the scientists in Italy who would guard their knowledge and not publish anything because it was a way to maintain employment. So how you would get a professorship in an Italian university is, you would go and present to the students and if they felt you were knowledgeable, they’d say yes, this person should be part of our system, so people didn’t want to publish anything because it would ruin their brand, they kept things secret.
>
>So what Cardano would do, he would get people very drunk and learn all of their secrets and he wrote them all down and then he eventually published books about this, which was super taboo and included how to factor quartic polynomial …he got that from Tartaglia[^100] …which means the stutterer. So he was a legendary guy and I think he was even a contemporary of DaVinci and I figured it’d be the perfect name for a cryptocurrency because the cryptocurrency is not good or bad, it’s a neutral thing, it’s brilliant and inspired, it’s a bit of a polymath and everybody has an opinion about it and you’ll never get a clear and concise way, but it certainly has a huge impact and it’s a man of its time.
>
>But then the other thing is that when you have cryptocurrency, you have the protocol name, then you have the currency name. In Bitcoin, it’s Bitcoin, it’s the same, but in other systems they’re different. So, what I decided to do with Cardano is I named the currency, Ada, after Ada Lovelace.[^101] She was a pioneering figure in the 19th century, the first female programmer of note, good friends with Charles Babbage, and left a great legacy and inspired generations of women that came after her to enter into the sciences and become developers. I’d like to say the 20th century spiritual successor to Ada Lovelace is Grace Hopper, creator of COBOL (Common business-oriented language) and also the gal responsible for the computer bug, there’s a great legacy there as well.
>
>When we were naming the Cardano ecosystem and thinking carefully about the name, the protocol, and what to name the currency, I wanted to connect every part of Cardano to historical figures who did something unique and special in their lives, not necessarily the best of people. Like for example, Cardano himself was a polymath and a brilliant mathematician, but he was also a little bit of a scoundrel from time to time. In fact, if you read his biography, it’s a surprise to me that Hollywood hasn’t made a book or a movie yet about Cardano, because he’s an incredible guy, but Ada is one of the good ones and she lived an incredible life and left an incredible legacy.
>
>And then I named every major release of Cardano after, either a famous poet or famous computer scientist, or somebody I was inspired by. So, for example, Byron was after Lord Byron. Then the next thing, Goguen is a world-famous computer scientist, who did a lot of work I admire.
>
>Lord Byron is one of my favorite poets, he wrote She Walks in Beauty.[^102] So I said it’d be cool to get a Byron connection and bring this in. I also wanted a balance, if I named something after a guy, I’d like to name something after a girl. So always have a nice balance between the feminine and masculine inside the system. That's where that came from. 

**Where did the naming scheme come from in Cardano?** CH explains:

>They’re just all people that I admired in my life… Voltaire’s work, and I read Shelley’s work, and some of the things were cautionary tales, - like Percy Shelley wrote Ozymandias[^103] for example.
>
>The name Shelley is interesting, there’s actually two famous Shelleys. There’s Mary Shelley and Percy Shelley. A lot of people think it’s Mary Shelley because she’s the more famous of the two. She wrote Frankenstein and a lot of other books, and her husband Percy was a famous poet, he was also a member of the Illuminati and he traveled the world and was an artist. He did a lot of cool things, so actually, I named Shelley after Percy, but at this point so many people confuse it for Mary. I say take your pick. The point of it was, that no matter how great a centralized system is, there’s this concept that eventually time takes its place and so Shelley wrote a very famous poem called Ozymandias about a traveler who went to Egypt, and he saw all these ruined monuments from long long ago, and he was just commenting on the fact that they’re all decaying now.
>
>So, I kind of looked at it the same way, that all things must change no matter how great your original ideas are. Time takes its place, so it’s kind of a reminder these systems require constant vigilance, updates, and maintenance to actually sustain themselves. It’s now in the hands of not a leader, but the community to do that with Shelley. So, I felt that was a proper way of naming it, but when I said the release was named Shelley, everyone just assumed it was Mary and they were quoting Frankenstein when it came out and I said, ‘damn it. Okay, it’s Mary if you want, they were married, so it kind of works.’ Anyway, it’s been overwhelmingly well received.[^104]

**Why the bull’s head symbol for the Daedalus wallet?** CH:[^105]

>That is not a bull’s head, that is a minotaur's head. The minotaur was a mythological creature that lived in the labyrinth. We named Daedalus after Daedalus the historical figure, or mythological figure, the father of Icarus and the creator of the maze. The labyrinth was built because no chains could bind the minotaur and so, by basically building a giant maze and putting the minotaur in it, he couldn’t escape the maze. So Daedalus is the name of the Cardano wallet. Daedalus is the creator of the labyrinth, and the minotaur is the most prominent creature within the labyrinth, that’s why the symbol is a minotaur.

**Byron** is named after the Romantic poet who was the father of Ada Lovelace. The British Library[^106] described him as ‘Dedicated to freedom of thought and action, and anarchic in his political views and personal morality, the poet and adventurer Lord Byron was the personification of the Romantic hero.’ 

Lord Byron was an English poet, peer, and politician who became a revolutionary in the Greek War of Independence and is considered one of the historical leading figures of the Romantic movement of his era. He is regarded as one of the greatest English poets and remains widely read and influential. Among his best-known works are the narrative poems Childe Harold’s Pilgrimage and Don Juan, a lengthy satiric poem where Byron portrayed Juan as someone easily seduced by women, reversing the legend of Don Juan as an actual womanizer.

He traveled extensively across Europe, especially in Italy, where he lived for seven years in the cities of Venice, Ravenna, and Pisa. During his stay in Italy, he frequently visited his friend and fellow poet, Percy Shelley. Later in life, Byron joined the Greek War of Independence fighting the Ottoman Empire and died of disease leading a campaign during that war, for which Greeks revere him as a national hero. Often described as the most flamboyant and notorious of the major Romantics, Byron was considered a celebrity in his era both for his success as a romantic poet and for his aristocratic excesses, which included huge debts and many sex scandals – numerous love affairs with both men and women. One of his lovers, Lady Caroline Lamb, summed him up in the famous phrase ‘mad, bad, and dangerous to know’. His only legitimate child, Ada Lovelace, is regarded as a foundational figure in the field of computer programming. Cardano ticker, ADA, is named after her first name, and her surname Lovelace is used to describe smaller units of ada tokens. 1m lovelaces = 1ada

**Goguen:** Joseph Goguen was a US computer scientist. He was a professor of Computer Science at the University of California and the University of Oxford and held research positions at IBM and SRI International. Goguen’s work was one of the earliest approaches to the algebraic characterization of abstract data types and he originated and helped develop the OBJ[^107] family of programming languages. Goguen studied the philosophy of computation, formal methods, and functional programming. He inspired Cardano with his work to build the K framework to verify the code of smart contracts, so they can be automatically checked for errors. Goguen was and advisor to Grigore Roșu[^108] when Grigore was at University of California. Grigore is chief executive of Runtime Verification who continue much of this work[^109] today. CH:[^110]

>By the way, I really regret this one. I shouldn't have named it Goguen, this should have been called Hopper after Grace Hopper. I like Goguen, he's a good guy, but there's not enough women here (on the roadmap).

**Basho:** Matsuo Basho was the most famous poet from Japan’s 17th century Edo period. He wrote short 3 sentence poems. One of his most famous poems is called Old Pond which describes how a frog, by doing small jumps, can reach the big ocean. The analogy being, as Cardano grows and new users onboard, the system will scale and be seaworthy for the ‘ocean’. CH:

>Basho went on this crazy journey during the Edo period in Japan when everybody lived in their silos there, you weren’t allowed to travel, but he was a guy who traveled and somehow didn’t get killed, and he wrote about all these crazy journeys.

**Voltaire:** Named after the French philosopher who prized criticism and argued for the separation of church and state. Voltaire, one of Charles Hoskinson’s favorite poets, was a versatile and prolific writer, producing works in almost every literary form, including plays, poems, novels, essays, and historical and scientific works. He wrote over 20,000 letters and over 2,000 books and pamphlets. He was an outspoken advocate of civil liberties, despite the risk this placed him in under the strict censorship laws of the time. As a satirical polemicist, he frequently made use of his works to criticize intolerance, religious dogma, and the French institutions of his day.

**Yoroi** is a ‘light client’ mobile wallet[^111] for Cardano. In Japanese, Yoroi means armor. It was built to protect the integrity of the samurai back in the Middle Ages.

**Ouroboros** is the name of Cardano’s network consensus protocol. The Ouroboros is an ancient symbol (‘tail devourer’ in Greek) depicting a snake or a dragon, eating its own tail, a fertility symbol also representing eternity and endless return.  

**Jörmungandr**[^112] is a node implementation, written in Rust,[^113] with the initial aim to support the Ouroboros type of consensus protocol on the incentivized testnet in 2019, then subsequently repurposed to be part of Catalyst. A node is a participant of a blockchain network, continuously making, sending, receiving, and validating blocks. Each node is responsible to make sure that all the rules of the protocol are followed. Jörmungandr refers to the Midgard Serpent in Norse mythology. It is an example of an Ouroboros, the Ancient Egyptian serpent, who eat its own tail, as well as the IOG paper[^114] on proof-of-stake.

**Plutus** is the Greek god of wealth. He was made blind by Zeus, because Zeus wanted him to be able to disperse his gifts without any prejudices and discrimination. Plutus[^115] is a smart contract platform for Cardano. Plutus contracts consist of parts that run on the blockchain (on-chain[^116] code) and parts that run on a user’s machine (off-chain or client code). Plutus draws from modern language research to provide a safe, full-stack programming environment based on Haskell, the leading functional programming language.

**Marlowe:** Named after Christopher Marlowe, an Elizabethan ‘forger, a brawler, a spy, but above all a playwright, a poet and the most celebrated writer of his generation’[^117] who was killed at the age of 29 in a drunken brawl over a bill but might have been assassinated. Marlowe, also known as Kit Marlowe, was an English playwright, poet and translator. He greatly influenced William Shakespeare, who was born in the same year as Marlowe. He was for anti-intellectualism, which is a form of hostility and mistrust of intellectuals.

In Cardano, Marlowe is a new domain-specific language[^118] (DSL) for modeling financial instruments as smart contracts on a blockchain. It is embedded in the Haskell language, which has its own established ecosystem and testing framework. You do not need programming expertise to use Marlowe and you can explore your Marlowe financial contracts with a browser-based contract editor and simulator.


[^1]: Surprise AMA! 12/12/2020, youtube.com/watch?v=GlVU8ZiVUL0
[^2]: **Ledger:** a distributed ledger (also called a shared ledger or referred to as distributed ledger technology) is a consensus of replicated, shared, and synchronized digital data geographically spread across sites, countries, or institutions. There is no central administrator or centralized data storage.
[^3]: In telecom networks, a **node** is either a redistribution point or a communication endpoint. The definition of a node depends on the network and protocol layer referred to. A physical network node is an active electronic device that is attached to a network, and is capable of creating, receiving, or transmitting information over a communications channel.
[^4]:  **Block**: a record of recent network transactions. Each block also includes the data necessary for blockchain management, such as an encrypted record of the preceding block. Each finished block is followed by the creation of the next block to continue the chain.
[^5]: A **cryptographic hash** is a math algorithm that maps data of an arbitrary size (often called the ‘message’) to a bit string of a fixed size (the ‘hash value’, ‘hash’, or ‘message digest’). It is a one-way function, that is, a function that is practically impossible to invert. Cryptographic hash functions are a basic tool of modern cryptography.
[^6]: **Address:** a data structure used to express different types of information in transaction outputs. To identify between various networks (eg, mainnet or testnet), each address has a network discriminant tag and a proof of ownership (who owns the transaction output). Delegation options and script references are also included in some addresses.
[^7]: **Reward:**  an amount contained in each new block that is paid out to the stakeholder by the network.
[^8]: Coined by Vitalik Buterin, who led the creation of Ethereum, the ‘**blockchain trilemma**’ sets out the challenges developers face in creating a blockchain that is scalable, decentralized and secure, without compromising on any facet. Blockchains are forced to make trade-offs between these three aspects: **Decentralization**: creating a blockchain system that does not rely on a central point of control. **Scalability**: the ability of a blockchain to handle a growing number of transactions. **Security:** the ability of a blockchain to operate as expected, and defend itself from attacks, bugs, and other unforeseen issues.
[^9]: **Slashing** is a mechanism used by some PoS protocols (but not Cardano) to discourage harmful behavior and make validators more responsible. They help keep the network secure because, without slashing penalties, a validator can use the same node to validate blocks on more than one chain or do so on the wrong chain
[^10]:  Nobody Knows When Ethereum Stakers Will Be Able to Withdraw Their ETH, beincrypto.com/nobody-knows-when-ethereum-stakers-will-be-able-to-withdraw-their-eth/
[^11]:  A **pure function** is a function that has the following properties: first, its return value is the same for the same arguments (no variation with local static variables, non-local variables, mutable reference arguments or input streams from input-output devices); second, its evaluation has no side effects (no mutation of local static variables, non-local variables, mutable reference arguments or inputs and outputs)
[^12]: MMT Chakravarty, S Coretti, M Fitzi, P Gazi, P Kant, A Kiayias, and A Russell (2020) ‘Hydra: fast isomorphic state channels’. eprint.iacr.org/2020/299.pdf
[^13]: In the decentralized ecosystem, a Layer 1 refers to the blockchain protocol itself. Layer 2 refers to a technology that operates on top of a blockchain to improve its scalability and efficiency. For example, Bitcoin is a Layer 1 network, and the Lightning Network is a Layer 2 to improve transaction speeds. Hydra is a layer 2 protocol built on top of Cardano, layer 1
[^14]: **Stake pool**:  a stable, block-producing server node that aggregates the stakes of several stakeholders (in Cardano’s case, ada holders) into a single entity, or pool.
[^15]:  **Saturation**: a stake pool is saturated when it has more stake delegated to it than is optimal for the network. The saturation level is expressed as a percentage. When a stake pool achieves 100% saturation, the rewards start to shrink. The saturation mechanism was created to avoid centralization by encouraging ada owners to delegate to several stake pools, and operators to build more pools to keep receiving maximum rewards. Saturation aims to safeguard both the interests of ada holders delegating their stake and the interests of stake pool operators (SPOs).
[^16]: Blockchain **governance** brings together norms and culture, laws and code, and the people and the institutions that are needed to run a system and ensure its stability in the long term. Governance, including voting and a treasury for long-term funding, is the focus of the Voltaire stage of the Cardano roadmap
[^17]: **Project Catalyst** is a series of experiments that seek to encourage the highest levels of community innovation. Catalyst is bringing on-chain governance to Cardano by allowing the community to determine priorities for growth (see Chapter 9)
[^18]: Let's talk Cardano - Interview with Charles Hoskinson, youtube.com/watch?v=NX3fGKMd004
[^19]: Essential Cardano Dev updates, essentialcardano.io/development-update
[^20]: How IOG’s research spans the academic world, iohk.io/en/blog/posts/2022/10/25/how-iog-s-research-spans-the-academic-worl
[^21]: **Functional programming** is a rigorous style of building the structure and elements of computer programs that treats computation as the evaluation of mathematical functions and avoids changing the properties of the data being processed. It is a ‘declarative’ paradigm in that programming is done with expressions or declarations instead of statements. In functional code, the output value of a function depends only on its arguments, so calling a function with the same value for an argument always produces the same result. This is in contrast to imperative programming where, in addition to a function’s arguments, the global state of a program can affect a function’s resulting value. Eliminating side-effects, that is, changes in state that do not depend on the function inputs, can make understanding a program easier, which was one of the motivations for the development of functional programming
[^22]:  Prof Aggelos Kiayias, ‘The Ouroboros path to decentralization’, iohk.io/en/blog/posts/2020/06/23/the-ouroboros-path-to-decentralization/
[^23]: Byzantine fault tolerance (BFT): A Byzantine fault is a condition of a computer system, particularly distributed computing systems, where components may fail and there is imperfect information on whether a component has failed. The term takes its name from an allegory, the ‘Byzantine Generals Problem’, developed to describe a situation in which, to avoid catastrophic failure of the system, the system’s actors must agree on a concerted strategy, but some of these actors are unreliable.
[^24]: **Slot**: Within an epoch, a set duration of time. Time is separated into numbered slots for each epoch. Active slots are those that are occupied by blocks
[^25]: In cryptography, a **verifiable-random function (VRF)** is a pseudo-random function that provides publicly verifiable proofs of its outputs’ correctness
[^26]: **Epoch**: a set group of slots that constitute a period of time (currently 5 days).
[^27]: A **script** is a generic term for an executable program used in the ledger. In the Cardano blockchain, these are written in Plutus Core.
[^28]: A **decentralized application** (dApp, dApp, or Dapp) is an open-source project that runs on a blockchain network. The distributed nature of these networks provides users with transparency, decentralization, and resistance to attacks.
[^29]: IOG audits, github.com/input-output-hk/external_audits
[^30]: Some Brief Comments on Process, youtube.com/watch?v=T4hjGjredpw
[^31]: The Boolean satisfiability problem (abbreviated **SATISFIABILITY** or **SAT**) is the problem of determining if there exists an interpretation that satisfies a given Boolean formula. It asks whether the variables of a given Boolean formula can be consistently replaced by the values TRUE or FALSE in such a way that the formula evaluates to TRUE. If this is the case, the formula is called satisfiable. On the other hand, if no such assignment exists, the function expressed by the formula is FALSE for all possible variable assignments and the formula is unsatisfiable
[^32]: ‘Country ranking’, ccaf.io/cbeci/index/comparisons
[^33]: Oettler (2022), ‘Nothing at stake / Costless Simulation’, blockchain-academy.hs-mittweida.de/courses/game-theory-blockchain/lessons/attacks-on-proof-of-stake-pos/topic/nothing-at-stake-costless-simulation/
[^34]: Anthony Quinn, ‘Combinator makes easy work of Shelley hard fork’, iohk.io/en/blog/posts/2020/05/07/combinator-makes-easy-work-of-shelley-hard-fork/
[^35]: **Staking** involves holding funds in a cryptocurrency wallet to support the security and operations of a blockchain network, and in return receive staking rewards. In other words, staking is the process of actively participating in transaction validation (similar to mining) on a proof-of-stake (PoS) blockchain.
[^36]: A **multi-asset (MA) ledger** can do the accounting for or interact with more than one type of asset. Cardano uses native tokens to provide this feature.
[^37]: **Plutus**: a Turing-complete programming framework for constructing functional smart contracts. Plutus is a Haskell-based programming language.
[^38]: A system is said to be **Turing complete** if it can be used to simulate any Turing machine. This means that this system is able to recognize or decide other data-manipulation rule sets. Turing completeness is used as a way to express the power of such a data-manipulation rule set. Virtually all programming languages today are Turing complete. The concept is named after English mathematician and computer scientist Alan Turing.
[^39]: The **Unspent Transaction Output (UTXO)** model is commonly used in the field of Distributed Ledger Technology (DLT) to transfer value between participants. A UTXO is the technical term for the amount of digital currency that remains after a cryptocurrency transaction. You can think of it as the change you receive after buying an item. Much more on this later, Chapter 5.
[^40]: **Metadata**: a collection of extra data expressing transaction circumstances or owner information. Metadata is used in smart contracts to indicate the circumstances under which a transaction should take place.
[^41]:  Adam Hayes, (2022) ‘10 important cryptocurrencies other than Bitcoin’, investopedia.com/tech/most-important-cryptocurrencies-other-than-bitcoin
[^42]: **Dogecoin** is a cryptocurrency featuring a likeness of the Shiba Inu dog from the ‘Doge’ internet meme as its logo. Introduced as a ‘joke currency’ in 2013, Dogecoin quickly developed its own online community and reached a capitalization of US$1bn in 2018.
[^43]: **Ergo** (ergoplatform.org) is a proof-of-work smart-contract platform that enables new models of financial interaction, underpinned by a safe and rich scripting language built with flexible and powerful zero-knowledge proofs (Σ-protocols).
[^44]: **Peer review** is the evaluation of work by one or more people with similar competences as the producers of the work (peers). It functions as a form of self-regulation by qualified members of a profession within the relevant field. Peer review methods are used to maintain quality standards, improve performance, and provide credibility. In academia, scholarly peer review is used to determine an academic paper's suitability for publication.
[^45]: ‘Polkadot consensus’, wiki.polkadot.network/docs/learn-consensus
[^46]: A Kiayias, A Russell, B David, R Oliynykov (2017) ‘Ouroboros: A provably secure proof-of-stake blockchain protocol’ citations, scholar.google.com/scholar?cites=9760004817031418890&as_sdt=2005&sciodt=0,5&hl=en
[^47]:  J Garay, A Kiayias, N Leonardos (2014) ‘The bitcoin backbone protocol: analysis and applications’, eprint.iacr.org/2014/765.pdf
[^48]: Cardano roadmap, roadmap.cardano.org/en/
[^49]: A **cryptocurrency wallet** stores the public and private keys which can be used to receive or spend a cryptocurrency. A wallet can contain many public keys but only one private key, which must be kept safe from loss or theft. Once a private key is lost that ends the life of that wallet. The cryptocurrency itself is not in the wallet. The cryptocurrency is decentrally stored and maintained in a publicly available ledger called the blockchain. Every piece of cryptocurrency has a private key. With the private key, it is possible to digitally sign a transaction and write it in the public ledger, in effect spending the associated cryptocurrency.
[^50]:  Cardano Explorer, explorer.cardano.org/en
[^51]: **Delegation**: By delegating the stake related to their ada holdings to a stake pool, ada owners participate in the network and collect rewards each epoch (five days). Delegators are rewarded in proportion to the amount of stake delegated.
[^52]: **Slot leader**: an elected node that has been chosen to construct a block in the current slot. An arbitrary election takes place based on the proportionate stake.
[^53]: How to buy Cardano ada cryptocurrency for beginners, youtube.com/watch?v=3MEO-Im6OSg
[^54]: Cardano wallets, cardanocube.io/collections/wallets
[^55]: How to choose a stake pool, iohk.zendesk.com/hc/en-us/articles/900002174303-How-to-choose-a-stake-pool
[^56]: How safe is it to delegate to a stake pool?, iohk.zendesk.com/hc/en-us/articles/900002046123-How-safe-is-it-to-delegate-to-a-stake-pool-
[^57]: How to delegate to a stake pool, iohk.zendesk.com/hc/en-us/articles/900005718683-How-to-Delegate-to-a-stake-pool
[^58]: Staking and delegating for beginners, forum.cardano.org/t/staking-and-delegating-for-beginners-a-step-by-step-guide/36681
[^59]: How to delegate from the Yoroi wallet, forum.cardano.org/t/cardano-shelley-how-to-delegate-from-the-yoroi-wallet/38230
[^60]: cardano-node, github.com/IntersectMBO/cardano-node
[^61]: IOHK | Cardano Whiteboard; overview with Charles Hoskinson, youtube.com/watch?v=Ja9D0kpksxw
[^62]: **First-principles thinking** is one of the best ways to reverse-engineer complicated problems and unleash creative possibilities. Sometimes called ‘reasoning from first principles,’ the idea is to break down complicated problems into basic elements and then reassemble them from the ground up.
[^63]: Scorex project, github.com/input-output-hk/Scorex
[^64]: IOHK research papers, iohk.io/research/library/
[^65]: The **Transmission Control Protocol (TCP)** is one of the main protocols of the Internet Protocol (IP) suite. Therefore, the entire suite is commonly referred to as TCP/IP. TCP provides reliable, ordered, and error-checked delivery of a stream of octets (bytes) between applications running on hosts communicating via an IP network. Major internet applications such as the World-Wide Web, email, and file transfer rely on TCP.
[^66]: Why Cardano?, why.cardano.org/
[^67]: Duncan Coutts, ‘Cryptocurrencies need a safeguard to prevent another DAO disaster’, iohk.io/blog/cryptocurrencies-need-a-safeguard-to-prevent-another-DAO-disaster/
[^68]: In defense of peer review, youtube.com/watch?v=3-rbn73cUEk
[^69]:  **Separation of concerns** is a design principle for separating a computer program into distinct sections, so that each section addresses a separate concern. A concern is a set of information that affects the code of a computer program.
[^70]:  Hoskinson announces a new system to tackle both security & privacy concerns, ambcrypto.com/hoskinson-announces-a-new-system-to-tackle-both-security-privacy-concerns/
[^71]: Wet code and dry, unenumerated.blogspot.com/2006/11/wet-code-and-dry.html
[^72]: The **semantic gap** characterizes the difference between two descriptions of an object by different linguistic representations, for instance languages or symbols. According to Hein, the semantic gap can be defined as "the difference in meaning between constructs formed within different representation systems". In computer science, the concept is relevant whenever ordinary human activities, observations, and tasks are transferred into a computational representation.
[^73]: The **Ring of Gyges** is a mythical, magical artifact mentioned by the philosopher Plato in his *Republic*. It grants its owner the power to become invisible at will. Through the story of the ring, *Republic* considers whether an intelligent person would be just, if they did not have to fear reputational damage if they committed injustices.
[^74]: Ari Juels, Ahmed Kosba, and Elaine Shi, ‘The Ring of Gyges: using smart contracts for crime’, arijuels.com/wp-content/uploads/2013/09/Gyges.pdf
[^75]: **RootStock** is a smart-contract peer-to-peer platform built on top of the Bitcoin blockchain. Its goal is to add value and functionality to the core Bitcoin network by the implementation of smart contracts as a sidechain.
[^76]: **Solidity ** is an object-oriented programming language for writing smart contracts. It is used for implementing smart contracts on various blockchain platforms, most notably, Ethereum.
[^77]: Jeevak Kasarkod, ‘Zeppelin: a secure smart contracts open-source framework for blockchain applications’, infoq.com/news/2016/10/zeppelin-secure-smart-contracts/
[^78]: Liquid Haskell, ucsd-progsys.github.io/liquidhaskell-blog/
[^79]: Why Cardano? CCL, why.cardano.org/en/introduction/cardano-computation-layer/
[^80]: Broadly speaking, **modularity** is the degree to which a system’s components may be separated and recombined, often with the benefit of flexibility and variety in use. The concept of modularity is used primarily to reduce complexity by breaking a system into varying degrees of interdependence and independence across and ‘hide the complexity of each part behind an abstraction and interface.’
[^81]: A **combinator** is a technical term used to indicate the combination of certain processes or things. In the case of Cardano, a hard fork combinator combines protocols, thereby enabling the Byron-to-Shelley transition without system interruption or restart. It ensures that Byron and Shelley ledgers appear as one ledger.
[^82]: Post Conference recap, thoughts and an AMA 04/21/2019, youtu.be/pBXZVrBQ6U8?t=3325
[^83]: **Permissioned v permissionless**. At the simplest level, the distinction lies in whether the design of the network is open for anyone to participate – permissionless – or limited only to designated participants, or permissioned.
[^84]:  Thoughts on cross chain communication, sidechains, NiPoPoWs and Litecoin, youtube.com/watch?v=HvIAgDEUC4o
[^85]: **Blockstream** is a blockchain technology company led by co-founder Adam Back. Blockstream intends to develop software to ‘break off’ transactions from the bitcoin network and charge a fixed monthly fee to allow people to use alternative ‘sidechains’. Blockstream employs a large number of prominent Bitcoin Core developers.
[^86]: Special Edition New Year’s AMA 2020, youtu.be/GtWt68kp1dg?t=777
[^87]: Chancellor on the brink of second bailout for banks, coindesk.com/podcasts/the-breakdown-with-nlw/13-years-on-the-meaning-of-chancellor-on-the-brink-of-second-bailout-for-banks/
[^88]: ‘Now that India has pulled back from banning crypto, here’s how it plans to develop digital currency on its own terms’, fortune.com/2022/02/02/india-crypto-ban-plans-develop-digital-currency-taxes-regulation-bitcoin/
[^89]: Special Edition New Year’s AMA 2020, youtu.be/GtWt68kp1dg?t=7282
[^90]: BitConnect Founder Indicted in Global $2.4 Billion Cryptocurrency Scheme, justice.gov/opa/pr/bitconnect-founder-indicted-global-24-billion-cryptocurrency-scheme
[^91]: What We Can Learn From OneCoin, Crypto’s Biggest Scam, fool.com/the-ascent/cryptocurrency/articles/what-we-can-learn-from-onecoin-cryptos-biggest-scam/
[^92]: Payments for $9 billion bitcoin settlement from Mt. Gox collapse could start in months, markets.businessinsider.com/news/currencies/mt-gox-bitcoin-settlement-payouts-9-billion-dollars-early-2022-2021-11
[^93]: Federal Court Orders BitMEX to Pay $100 Million for Illegally Operating a Cryptocurrency Trading Platform and Anti-Money Laundering Violations, cftc.gov/PressRoom/PressReleases/8412-21
[^94]: **Howey Test:** Securities and Exchange Commission (SEC) v. W. J. Howey Co. (1946). The case resulted in a test, known as **the Howey test**, to determine whether an instrument qualifies as an ‘investment contract’ for the purposes of the Securities Act: ‘a contract, transaction or scheme whereby a person invests his money in a common enterprise and is led to expect profits solely from the efforts of the promoter or a third party. The Howey Test has remained a notable determiner of regulatory oversight for many decades. In the past few years, it has been called into question, most frequently in conjunction with discussions about Cryptocurrencies and Blockchain technology’.
[^95]: The Future of Digital Asset Regulation, youtube.com/watch?v=K4ZM2AlGT-s
[^96]: Cardano founder steals the show at Congressional hearing on crypto regulation, cryptoslate.com/cardano-founder-steals-the-show-at-congressional-hearing-on-crypto-regulation/
[^97]: **M-Pesa** (M for mobile, pesa is Swahili for money) is a mobile phone-based money transfer, financing and microfinancing service, launched in 2007 by Vodafone for Safaricom and Vodacom, the largest mobile network operators in Kenya and Tanzania. It has since expanded to Afghanistan, South Africa, India and in 2014 to Romania and in 2015 to Albania. M-Pesa allows users to deposit, withdraw, transfer money and pay for goods and services (Lipa na M-Pesa) easily with a mobile device.
[^98]: **Kiva** (commonly known by its domain name, Kiva.org) is a non-profit organization, the world’s first online lending platform connecting online lenders to entrepreneurs across the globe. Kiva’s mission is ‘to expand financial access to help underserved communities thrive.’
[^99]:  Best of all possible worlds, everipedia.org/wiki/lang_en/Best_of_all_possible_worlds
[^100]: Some Random Thoughts and Updates, youtu.be/ttFptsL5hN0?t=4353
[^101]: Tartaglia, everipedia.org/wiki/lang_en/Niccol%25C3%25B2_Fontana_Tartaglia
[^102]:  Happy Birthday ADA!, youtu.be/hhAOJyi_3lA?t=27
[^103]: She Walks in Beauty, poetryfoundation.org/poems/43844/she-walks-in-beauty
[^104]: Ozymandias, poetryfoundation.org/poems/46565/ozymandias
[^105]: Charles Hoskinson - Building a Better World with the Blockchain, podcasts.apple.com/us/podcast/charles-hoskinson-building-a-better-world/id1553861681?i=1000517944232
[^106]: Special Edition New Years AMA 2020, youtu.be/GtWt68kp1dg?t=8496
[^107]: Lord Byron, bl.uk/people/lord-byron
[^108]: OBJ programming language, everipedia.org/wiki/lang_en/OBJ_%28programming_language%29
[^109]: Grigore Rosu, runtimeverification.com/blog/author/grigore-rosu/
[^110]: Cardano360 - March 2021, youtu.be/ULBLgPgxtN8?t=1571
[^111]:  IO ScotFest Keynote with Charles Hoskinson, youtu.be/tbtkClr3Y3I?t=356
[^112]: Yoroi mobile wallet, yoroi-wallet.com/
[^113]: Jormungandr, everipedia.org/wiki/lang_en/J%C3%B6rmungandr
[^114]: **Rust** is a lightweight, portable programming language from Mozilla that compiles to the web, iOS and Android. Rust is a multi-paradigm, general-purpose language designed for performance and safety, especially safe concurrency.
[^115]: Kiayias, Russell, David, Oliynykov (2019) 'Ouroboros: A Provably Secure Proof-of-Stake Blockchain Protocol', eprint.iacr.org/2016/889.pdf
[^116]: Plutus, developers.cardano.org/en/programming-languages/plutus/overview/
[^117]:  **Off-chain code**: The part of a contract application’s code which runs off the chain, usually as a contract application. On-chain code: The part of a contract application’s code which runs on the chain (i.e. as scripts).
[^118]: Marlowe, bbc.co.uk/programmes/p003k9d6
[^119]:  A **domain-specific language (DSL)** is a computer language specialized to a particular application domain. This is in contrast to a general-purpose language (GPL), which is broadly applicable across domains.


**_Rest of Chapter to be uploaded soon..._**

