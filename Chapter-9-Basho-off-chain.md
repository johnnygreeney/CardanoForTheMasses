# Chapter 9: Basho (Scaling off-chain)

‘Knowledge is knowing that a tomato is a fruit. 
Wisdom is knowing not to put it in a fruit salad.’                              

― Brian O'Driscoll


**TO DO: add markdown format**

Off-chain computing  

Offloading part of the computing, such as via Asynchronous Contract Execution (ACE), may improve the efficiency of the core network. Transactions take place outside of the blockchain, yet a trust model allows for quick and inexpensive transactions. This concept is still in research mode and will likely be implemented in a future update. Note there are also Cardano projects offering decentralized compute like Filecoin and Iagon (iagon.com). 
Mithril

Mithril allows users to get the current state of a blockchain without recovering its entire history. Instead of having to confirm every block since day 0, a node can join from a certified snapshot. Light, fast, efficient, and secure …Mithril is named after the fictional metal found in J. R. R. Tolkien's Middle-earth writings. It is lightweight but 'wrought of pure silver to the power and strength of triple steel'.

At the Cardano Summit 2021, IOG researchers Pyrros Chaidos and Roman Oliynykov presented Mithril – a new protocol and network based on the research paper by Chaidos and Prof Aggelos Kiayias. Mithril utilizes a stake-based threshold multi-signature (STM) scheme to solve chain synchronization, state bootstrapping, and trust issues in dApps. Mithril has evolved into an open-source project with an aggressive biweekly release cadence. The release process is constantly refined for a smooth developer experience.

The original paper, and related blog by Olga Hryniuk, are quite technical and outline the long-term vision for the protocol. Like all agile, open-source projects, the final implementation might vary. What is clear is the burning need for a solution like this to enable faster syncing to the blockchain.

Piggybacking on the security of Cardano’s staking system, Mithril enables stakeholders to vouch for some fact, with a weighting proportional to their stake. Mithril’s initial proof of concept is to bootstrap a full Cardano node, however, it is flexible to apply to other protocols. For example, its main feature of validating the state snapshot can be applied to data exchange between sidechains, roll-ups, on-chain voting... Any many-to-one scenario is a potential use case. 

Mithril is an overlay sitting on top of Cardano’s Layer 1 mainchain, allowing the network to create proof certificates. The certificates produced by Mithril have the same security properties that Ouroboros has. This has profound benefits. For example, millions of votes could take place off-chain, and then be aggregated together as a threshold signature. It would ultimately only be a single transaction on-chain. A full node like Daedalus can sync much quicker as a result.

How it works

The STM (stake-based threshold multi-signature) scheme described in the original research paper is now available as a stand-alone core library on GitHub. It contains the full set of primitives of the Mithril protocol and is stand-alone in that it’s blockchain agnostic, it can potentially run on any PoS blockchain. Indeed, it can even run without a blockchain: it's a Stake-based Threshold multisignature scheme that only assumes:

pub keys are exchanged and 
participants vote with some stake using the lottery algorithm then 
signatures are aggregated in a certain way

The Mithril Network sits on top of the Mithril Core library. There are three node types in the current proof of concept setup. 
The Mithril Signer is run by a (SPO) stake pool operator, side by side with the Cardano node. It signs the ledger state, ie. creates individual signatures.
The Mithril Aggregator collects the Signers’ signatures and creates multi-signatures, then embeds them in certificates. The aggregator also creates and stores the ledger state snapshot archive. These can be large, in the tens of GBs, and will grow as a blockchain grows.
The Mithril Client restores (bootstraps) a full Cardano node by taking a snapshot and its certificate chain from the Aggregator node and verifying their validity with Mithril cryptographic primitives.
The Mithril architecture diagram is not for the faint hearted and difficult to capture the scale in a book. If you want to dig deeper, go to Mike Hornan’s simplified graphic on the Cardano Forum. The Lottery analogy is often used to explain Mithril:
IOG Architect Arnaud Bailly speaking on Cardano360 May 2022
One analogy that you can use to think about it is a lottery. So depending on the amount of stake, you draw tickets from a lottery, and depending on the amount of stakes you draw, depending on the amount of tickets you bought, your chances of having a winning ticket are higher. And so this is the same for Mithril ...you can potentially have several winning tickets. Once enough winning tickets have been drawn, over all the stake pool owners, then a certificate can be issued which provides a certified signature of the current state of the chain from a share, some share of the stake pool owners, from some predefined share... and this is what we call a snapshot.
Now the snapshot is made available to clients, and the clients can verify it, they can verify these snapshots by checking the aggregate signatures from all the lottery winners, so to speak, and so from all the signers....and check that they are actually legit and this check also rests on checking that the stake distribution is legit, and this is done through checking the chain certificate down to some general certificate ...and once they have verified the validity of certificate, now they can just download the snapshot itself, bootstrap the node, without having to go through the hassle of verifying everything.

Progress to date

The Mithril Network was tested as a centralized version initially (IOG-operated Mithril Aggregator). This paved the way for a decentralized version on the Cardano testnet where SPOs run the Mithril Aggregators. At ScotFest, Jean-Philippe Raynaud’s demo showed how a Daedalus wallet synched 15 times faster with Mithril, compared to classical bootstrapping. Mithril is crucial for trustless light wallets as they would otherwise need a third party to sync blockchain history. Mithril will enable fast sync times but also benefit from the mainchain’s security properties. 
In early 2023, the Mithril team published an SPO on-boarding guide in preparation for mainnet release, which took place in July 2023. Later in October, the Mithril 2 research paper was published in partnership with Algorand researchers from Boston University. Mithril 2 uses ‘Approximate Lower Bound Arguments’ (ALBAs)  to prove knowledge of a large dataset without revealing the full dataset.
Romain Pellerin, IOG’s Chief Technical Officer, explained ALBAs have many use cases such as demonstrating possession of multiple digital signatures from different individuals, without revealing each signature. Charles Hoskinson was effusive in his praise for the paper:

Mithril 2 is out. I’m very proud of this paper. It’s damn fine work. 
‘Mythril 2 just came out… the ALBA construction really is as good as it gets, these compact certificates inside Mithril …so we're now at a point where I think it's prudent to start talking about integrating Mithril itself into the Cardano blockchain ledger itself….’

He revealed in the closing keynote of the Dubai Summit that Mithril could bootstrap Daedalus in the lab in 20 minutes, where it used to take 3 days. 
Zooming out, Mithril’s roadmap is based around these key milestones:

Mithril beta: mainnet launch with volunteer SPOs
Mithril MVP (2023): an incentivized protocol with additional features to support basic use cases, such as fast bootstrapping and secure light wallets.
Mithril (2024): a fully decentralized and self-sustaining Mithril ecosystem.

In 2024, just some of the highlights included a Mithril protocol insights dashboard and a manual setup guide for the relay in the SPO user guide. An overview of the protocol security was published in the documentation. The Mithril team also released CIP-137 - decentralized message queue, which will be used to diffuse Mithril signatures in the future.

Mithril hosts monthly open calls. In the November 2024 call, for example, Ouroboros Leios was discussed. To keep updated with the ferocious pace of development, read the weekly development updates on Essential Cardano every Friday, follow mithril.network and contribute to the Mithril repository on GitHub.

Looking to the future, Mithril now provides more than a full node DB snapshot. It provides transaction verifications so one can check whether or not some specific transactions are included in the chain at the point of the signature, and this is available in the browser so can be used by just any dApp or wallet.

Mithril recently started to provide certified stake distributions snapshots which are critical for verification of block headers. This paves the way for alternative nodes for example (eg. Amaru) to avoid having to sync the whole chain and deal with all the intricacies of past eras.
Hydra

Hydra introduces isomorphic state channels to increase throughput, decrease latency, save money with reduced transaction fees and storage needs. IOG developed Hydra as a solution for Cardano and related networks using a principled, evidence-based methodology. Hydra is the result of substantial research and a critical step toward allowing decentralized networks to grow securely to meet global demands. Hydra makes it easier to perform transactions off-chain while still utilizing the main-chain ledger for secure settlement. 

Hydra can sound very complicated and is sometimes confused with similar solutions. Let’s begin by clarifying what ‘isomorphic state channels’ are. ‘Iso’ is a prefix meaning equal, for example, isometric means equal measurements. ‘Morphic’ means relating to shape or form. So isomorphic means having the same structure and properties. 

‘State channels’ extend the notion of payment channels to also support smart-contracts over off-chain channels. Participants in the channel can now, in addition to traditional transactional payments, execute scripts to handle complex logic, off-chain, before committing the result back to the Layer 1 later.

Participants lock funds into a smart contract on Layer 1. They can then transact with others in the state channel, off-chain, in whatever fashion meets their use case pursuant to the operating rules of the head(s). Each transaction in the head requires all node operator's approval. Afterwards, the outcome is settled on-chain, without requiring the full transaction history of what occurred off-chain in the meantime. 

A powerful feature of Hydra is that existing smart contracts and solutions used for Cardano mainnet can be directly redeployed inside Hydra. Developers can leverage Cardano’s proven infrastructure to develop wallets and dApps that communicate with the layer 2 system, drastically reducing the learning curve for Hydra. A Hydra Head may also be formed without the need for any initial funds from the receiving party, ensuring a seamless user experience. 

Hydra protocols

Hydra is a distributed ledger scaling solution that meets all three of the aforementioned scalability challenges: high transaction throughput, low latency, and minimum storage per node. While Hydra is being developed in collaboration with the Ouroboros protocol and the Cardano ledger, it may also be used with other systems that have the same properties as Cardano.

Hydra’s overall aim is to provide a cutting-edge layer 2 scaling solution for Cardano. Hydra will save expenses while boosting throughput and ensuring security. Hydra replicates the main chain’s functionality while minimizing friction for users, but still allows the flexibility of having a different fee structure and timing constraints on the layer 2. 

Hydra is a system made up of many subprotocols that work together to solve a single problem: scalability. Cardano’s ecosystem is diverse, with numerous organizations with varied technological capabilities: the system needs to support stake pools, light wallets, DEXs, and other end-users with a variety of computing performance and availability characteristics. It’s unreasonable to expect a single-protocol, one-size-fits-all method to provide overall scalability for such a diverse group of network actors.

In an early blog, the Hydra architecture was broken down into four components: the head protocol, the tail protocol, the cross-head-and-tail communication protocol, as well as a set of supporting protocols for routing, reconfiguration, and virtualization. Although it was originally developed as part of the Ouroboros research agenda, it has taken its own route and is now an agile open-source project with a rapid release cadence. 

Hydra Head

The Hydra ‘head’ protocol was the first part of the Hydra architecture to be released. The Head protocol began to take shape in 2020, especially during this early implementation and proof of concept stage. IOG’s understanding has evolved since then, and 2022 saw the formalization and implementation of a variation on the ‘Head’ protocol in the original paper. 

Hydra acts as dApp-embedded software for developers seeking scalability. It is implemented in two parts:

On-chain scripts are primarily responsible for locking and releasing funds used within the Hydra head protocol
Hydra node, a software stack which provides a high-level interface using standard web technologies like WebSocket and JSON.

To operate a Hydra Head, a working Cardano node is a prerequisite. Note that this is a requirement that will soon be deprecated, allowing for the use of external Cardano nodes such as Blockfrost API based ones, making the Hydra node significantly lighter to operate.

You then run a Hydra node, connected to other Hydra nodes and a Cardano node. Each Hydra Head can consist of several Hydra nodes. On-chain code will be the same between Cardano and a hydra head. This is one of the major selling points of the hydra design. 

The potential Hydra Head topologies and use cases are listed in detail on the aptly named website https://hydra.family. The community is actively encouraged to give feedback on the roadmap. 

Hydra Head ‘Poker game’ analogy 

The Hydra Head protocol is best used where participants, well-known to each other, agree to form a network but don't trust each other with the funds. A Hydra Head enables them to do so with ways to secure their assets, backed by the ability to settle disputes on the Layer 1.

There are several use cases explained on the Hydra site, but the poker game is perhaps the most intuitive analogy to explain Hydra Heads. Consider Heads as a ‘private poker table’ where players bring their own chips to play with. The game may be played for as long as the participants like. If no one participates, the game will not advance. Participants are, however, able to leave with their chips. The game will terminate with the existing pot distributed if they do so. Incremental commits (in active testing) and incremental decommits, allow players to join or leave the table while the remaining players continue. 

A channel is a communication link between two or more peers. To be a part of a Head, you must be one of the peers. Channels establish isolated networks that may develop independently of the main network. Participants on these alternate networks use a different, simpler consensus algorithm: everyone must agree on all transactions that pass through. As a participant, I am unable to lose money that I have not specifically decided to lose. Why? Because every binding transaction needs my express permission.

Participants may make financial commitments to a Head while creating it. This entails transferring funds off-chain to a script address that binds them to a set of rules. The script ensures that the protocol is executed safely on-chain, and that participants cannot defraud one another. Any participant, however, may choose to leave the Head at any moment by closing it. In this situation, everyone gets the most recent state they consented to off-chain, on their parallel network.


Figure 9.1: Courtesy of Cardanians’s medium post ‘Hydra: Cardano Scalability Solution’
The on-chain script’s dealer at the table guarantees that everyone follows the rules and doesn’t cheat. In conclusion, there are the same number of chips out as there were before the game began, although they may have been rearranged throughout the game. While the ultimate outcome is known outside of the table, the players are the only ones who know the history of all bets taken throughout the game. The funds, or existing table pot, are unlocked based on the most recent agreed upon snapshot.



Figure 9.2: Hydra Head use cases, from ScotFest talk by Hydra Product Manager, Nebojša Vojvodić 

Evaluating the Hydra head protocol 

Hydra Heads are known for their ability to achieve near-instant finality inside a Head. Setting up and closing a Head might take a few blocks. Simulations have shown that a single Hydra head can reach up to 1,000 TPS (Transactions per second), so if 1,000 heads are run in parallel, it should be possible, in theory, to achieve a million TPS. 

So, is Hydra able to call whatever TPS number it wants? In principle, the answer is yes, which highlights a flaw in the common use of TPS as a system comparison measure. While it’s easy to simplify the complexity of evaluating protocol performance to a single number, a lofty TPS claim is almost worthless without further context. With this in mind it’s best to adopt the following practices:

explicitly describe all of the variables that affect the simulation: transaction size, time to verify a single transaction, time required for cryptographic procedures, allotted bandwidth per node, cluster size and geographical distribution, and transaction parallelism limitations.


evaluate the protocol’s performance on baselines that define the underlying network and hardware infrastructure’s exact and absolute bounds. How effectively one approaches such boundaries indicates how much space for progress there is. 

The research paper (Section 7: Simulations) has further information and graphics. The Hydra team regularly post testing results on the site and welcome more real-world test scenarios. Hydra started bearing fruits in 2022. Obsidian Systems and IOG announced Hydra for Payments which is an exciting prospect for micropayments on Cardano. At the Rare Bloom event in Denver, SundaeSwap demoed how their protocol could work as a Hydra Head. 

Hydra’s team lead at the time, Sebastian Nagel, presented at the 2022 Cardano Summit in Lausanne. The goal was now for Hydra to be the number one dApp on Cardano, regardless of how this is measured. 

Hydra Head is only the first part of a larger group of protocols as described in Chakravarty and co Hydra: Fast Isomorphic State-Channels. As Hydra matures and adoption grows, several topologies will be implemented. It’s best to check hydra.family for the latest roadmap. Current plans include a ‘Delegated Node’, a ‘Managed Hydra Head’ (aka Hydra as a Service) and a ‘Star-shaped Network’. 

Sep 21, 2022. Re: Hydra: CH

When you look at things like Mithril, Hydra… these are extensions of known concepts, like Mithril is a threshold signature idea, and they construct these proof certificates, and then when you do transactions, they're paired with proof certificates, and it gives you the inclusive accountability …it's not a new idea, it's like 10 years of talking about this stuff. We just implemented it. It's a lot of hard cryptography to implement, but once it's done it's done, and it's more about how do you distribute the certificate and build them?

Hydra is everything Lightning wanted to be when it grows up. The problem with Lightning is that it's not a hard protocol… payment channels and state channels. The hard part is the fact that Bitcoin is not programmable. So, 95% of your effort is trying to figure out how do you get a model, that's not designed for this, to work with this. 

It's almost like when they were upgrading the Hubble telescope in space, you know, after you've launched the telescope into space, it's not upgradable anymore, but yet NASA is like ‘well we need to fix it’. So, they sent astronauts out there, and they put this giant contact lens on it, and they had to figure out how to open shit that you really can only open on Earth, in space. So, you have this guy like basically wearing an oven mitt, with a very tiny screwdriver floating in space, trying to unscrew a panel and gradually upgrade old circuitry, and make it better without getting himself killed. So that's Bitcoin in a nutshell, when you try to apply Lightning. 

Well with Cardano, we're on Earth, okay, it's programmable meaning that we can always go and pull a module out, put a new module in, and do these things. So, with extended UTxO and Plutus, there's enough there that you can build rich isomorphic state channels. So basically, you can take state and assets, and you can batch and bundle them together, and put them into a layer 2 solution…and then you can use it for microtransactions, you can use it for smart contracts, but then you can build modules on top of it to do specific applications like DEXs, voting… these types of things. 

Oct 3, 2022. Re: Hydra, Let’s Talk Basho. CH

So the way that we designed Plutus is that you have an on-chain component, and that's your Plutus script… and then you have this idea of off-chain infrastructure that coordinates with the dApp to run things… and this is very common in the Ethereum model as well and they have all these things to combine these two, and then off-chain infrastructure sometimes is centralized, sometimes it's not centralized, it depends on the specific dApp. The idea of Hydra is that it would be part of that off-chain kit, so it would be embedded in dApps that require a lot of scale, and basically it would do something similar to what's occurring with Mithril, where you go many-to-one or some
Matthias Benkort’s retrospective blog post noted ‘one might say 2022 was about ramping up software quality and preparing Hydra for the first pioneers to build.’ In January 2023, IOG collaborated with Mlabs (mlabs.city) to produce the Implementing auction projects using Hydra paper. The study explores various ways to implement digital asset auctions using the Hydra Head protocol. This is central to how DEXs and NFTs will function on Cardano. The paper addresses current project needs and considerations in detail. 
The Hydra team explored integration with the wider ecosystem in 2023, for example, Hydra support for Kupo. They improved documentation with a Hydra node architecture explainer. They also updated the Hydra tutorial to simplify the getting started experience while also including Mithril to fast bootstrap the cardano-node. They worked closely with the Aiken team, exploring the idea of moving the Plutus validator scripts to Aiken. Elsewhere, demeter.run now offers a Hydra Head as a service through their platform Demeter (demeter.run).

Notable milestones included the release of the first mainnet-compatible Hydra node version. 

The Hydra project is a joint effort by engineers at IOG, but also the Cardano Foundation and a growing list of contributors. The Cardano Foundation deployed Hydra tally to mainnet so more community members could attest and verify validity of Catalyst Fund results. Previously, only IOG could tally votes. The experiment explores how Hydra could potentially decentralize the process.

As the work of the Hydra and Mithril teams converged more and more, Sasha Bogicevic (Hydra) and Franco Testagrossa (Mithril) delivered a masterclass at the Dubai Cardano Summit where they showed how the projects can work together. The Mithril and Hydra regularly hold joint monthly open meetings, to talk about progress and related scaling projects. 

Figure 9.3: Hydra Doom 

Hydra’s real world effectiveness has been demonstrated by powering the classic ‘first person shooter’ computer game Doom. Originally released back in 1993, its popularity has endured with a new release due in 2025. Doom running on Hydra through a classic arcade console has been a popular attraction at Cardano conferences answering an emphatic ‘yes’ to the common question in the gaming world ‘can it run Doom?’ Where each frame is a transaction, it wasn’t long before the mythical one million transactions per second milestone was surpassed.

The team behind Hydra Doom: Trym Bruset, Sebastian Nagel, Pi Lanningham, Josh Marchand and Adam Dean provide ongoing support for the Hydra Doom tournament. They have also integrated the CIP68 token standard into the game. This enables the token in a user’s wallet to reference a different token called the reference NFT for certain metadata. What does this mean? A user token can ‘update’ based on certain criteria, without them having to do anything. So the CIP68 token the user receives on mainnet could be an NFT music album but the music tracks can update based on what in-game levels the player reaches.

It wouldn’t be a family without other siblings, and more Hydra protocols are coming. Hydra Tail is in the early stages of research, and will extend the concept of isomorphic layer-2 solutions to roll-up-like protocols. Details about the other protocols are available onthe Hydra website, and in the upcoming Mastering Cardano book which will be more of a technical reference manual. Follow the latest progress on the Hydra Head roadmap.

The success of Hydra has spawned similar projects like Hydrozoa from George Flerovsky and Gummiworm by Sundae Labs.

Hydra clarifications

There has been some discussion promoting Hydra as the ‘ultimate’ be-all and end-all Cardano scalability strategy. Hydra Heads provide a solid basis on which to develop Cardano’s scalability layer. They are a critical building piece that allows more complicated solutions to be built on top of the Extended Unspent Transaction Output (eUTxO) architecture. They are an important part of the scaling journey, but they are not the end goal.

Mithril’s development is closely tied to that of Hydra, with overlapping teams. Some of Mithril’s components can connect and work fine with Hydra. Their websites, mithril.network and hydra.family, share a similar format with excellent quick start guides, glossary, etc. As they are both open-source projects, anyone can contribute to these pages on GitHub.

A Hydra Head is usually a relatively small-scale network created by a small number of people. Because these groups will be autonomous at first, looking at the total of their separate metrics is deceptive. Although Hydra Head protocol’s initial iteration will enable small groups of participants to scale up their traffic at a reasonable cost, it will not provide a solution for worldwide consumer-to-consumer (micro) payments or NFT sales right away. 

Why not? Because the consensus inside a Head necessitates each participant’s response to each transaction, everyone needs to agree on each transaction. While this offers security assurances to participants in a Hydra Head, it limits the total number of participants in practice. IOG, and the growing number of contributors to the project, continue to research ways to expand the Hydra Head protocol’s capabilities. In 2021, there was a paper released from Tokyo Institute of Technology titled Interhead Hydra: Two Heads are Better than One. It is an iteration on top of Hydra Head proposing a mechanism for linking two Hydra Heads together, allowing the formation of a network of linked Hydra Heads in the long term. 

There is a risk for non-participants as your funds are in the hands of the participants operating the Hydra Head. 


A Hydra Head protocol is not a sidechain. There are no blocks created in a Hydra Head, nor is there any transaction history available outside the Head. That said, the state history of a Head can be published fully or via other structures such as a Merkle tree to allow outside observers to validate the Head results after the fact. New participants cannot join an existing Head. They need to be there from the start as an operating Head is an isolated, private channel.
Sidechains 

A sidechain is a blockchain that is linked to a main blockchain (the mainchain, or parent chain) through a two-way mechanism (a ‘bridge’) that allows tokens and other digital assets from one chain to be utilized in another and the results to be shared back and forth. Multiple interoperable sidechains may be joined to a single parent chain, each of which can function in a different fashion. 
A sidechain is the exact same concept as a blockchain. The difference is philosophical, not technical. The sidechain usually aligns with the mainchain, but a sidechain can have its own business logic, cryptocurrency, monetary policy, consensus rules, programming language, application domain, subset of users, smart-contract capabilities, stablecoins, use cases like NFTs, loyalty points, etc. Sidechains are the same technically as a standalone blockchain, in that blocks are produced by validators. 
Unlike state-channels such as Hydra, they offer data-availability and participation for new users. In a state-channel, typically only participants of the channel can see what is going on in the channel, and they must be decided up front. Joining a sidechain is typically done by burning or locking assets on the mainchain, in return for an equal amount on the sidechain.
Cardano’s eUTxO model means the state is pre-sharded on the mainchain, so it’s easier to move state to a sidechain. Sidechains are ideal for medium to low-risk protocols. They are ideal for new, or growing ecosystems because the sidechain can avail of an established mainchain’s security, liquidity, wallets, and user participation. Sidechains lighten the load off layer 1 mainnet, all the while enjoying the veracity that’s provided by its parent chain. 

While there will be large transaction volumes running in parallel on sidechains, these transactions don’t reconcile on the mainchain so resources on the Layer 1 mainchain aren’t consumed by sidechains. 

IOG have been thinking about sidechains for quite some time, as far back as 2014, they reviewed Blockstream’s pegged sidechains paper. Then the was ScoreX, a flexible, modular blockchain framework that was built to enable blockchain experiments. It was an early IOG project before it was incubated at HyperLedger Labs. Ergo was just one example of a blockchain built using ScoreX. IOG has held regular talks with engineers at Hyperledger Fabric, an open source blockchain framework similar to ScoreX. They monitored the rise in popularity of Cosmos, a blockchain focussed on interoperability. More on Cosmos shortly. 

The sidechain strategy has been laid out as early as 2016, in the Why cardano? paper. The original proposal was for a CSL (Cardano Settlement Layer) and a CCL (Cardano Computation Layer). This vision manifested itself slightly differently in the sidechains model, in that there would be multiple CCLs.

A lot of deep thought and academic rigor went into Cardano’s architecture. It’s evident in how rewards incentivize sidechain partnerships. Ada holders traditionally get staking rewards in ada. The same SPOs that power the mainchain, will also provide staking liquidity for sidechains. So now, if the SPO you delegate to is also part of the sidechain SPO subset, you get rewards in that sidechain’s native asset in addition to your usual ada rewards. 

Re: Sidechains, Let’s Talk Basho. CH: 

It's basically like super-Hydra. Hydra is dApp-specific, sidechains are ecosystem-specific

There are often trade-offs to running a sidechain. Increased throughput can mean less security. Bridge security is challenging in practice and there have been many hacks. Indeed, Charles Hoskinson stated the only time he lost money due to a hack was the Nomad Bridge hack in 2022. However, Cardano offers a very secure layer 1 mainchain. Funds in a bridge contract are well protected and assets are securely transferred between sidechains based on the formal definition outlined in IOG’s 2019 Proof-of-Stake Sidechains paper. 

The research describes how a new ‘firewall’ security property protects a mainchain from its sidechains. Potential failures on the sidechain won’t impact the parent chain. Project Catalyst, for example, is run as a sidechain of Cardano. Even if its safety is compromised, no funds are lost on Cardano. The paper also outlines a blueprint describing merged staking, cross-chain certification, and multi-signature for proof-of-stake sidechains.

Based on this research, IOG developed the Cardano EVM (Ethereum Virtual Machine) sidechain, Mamba, following a deliberate and iterative approach. It was an open-source sidechain protocol with a client written in Scala. Mamba was compatible with Ethereum’s tools and libraries enabling developers to write Solidity smart contracts, dApps, and ERC20 tokens on Cardano. Ethereum smart contracts could run unchanged on Mamba, with much lower gas fees.

The consensus protocol used on Mamba was Ourorobos BFT. This was an earlier iteration of Ouroboros used on the Cardano mainnet. It is a simple, deterministic protocol for ledger consensus that tolerates Byzantine faults. There are different versions of proof-of-stake (PoS), which are suited to different use cases on sidechains and main chains. Sebastien Guillemot gives a breakdown of the trade-offs in his video Cardano & Algorand: Leader Selection Explained. 
Milkomeda  
Not everyone is enamored with Cardano’s current architecture. CTO and co-found of dcSpark, Sebastien Guillemot, questioned Cardano’s monolithic structure and why it has deviated from the initial vision in ‘Why Cardano?’. Having worked on the protocol since the incentivized testnet days, his views should be taken seriously. Having said that, there are trade-offs in any blockchain decisions. 

Cardano is an open ecosystem and people are free to launch sidechains using different models. The first Cardano sidechain was launched by dcSpark. Milkomeda brought EVM compatibility and a bridge for developers to the Ethereum ecosystem. Milkomeda is a portmanteau, named after the Milky Way and Andromeda galaxies which are due to merge in a few billion years. Milkomeda also brought EVM compatibility to Algorand as well, merging multiple ecosystems. What is interesting is Milkomeda was implemented differently on both blockchains. It was a Cardano sidechain, but a Layer 2 solution on Algorand. 

Guillemot explained the differences and reasoning at the Rare Bloom event. As discussed previously, a sidechain is a blockchain that aligns technically with a parent chain but differs philosophically on key features. Milkomeda C1, for example, was a Cardano sidechain where they chose to keep the same base asset (ada) but had faster block times (4 secs) with instant finality. It wasn’t possible to implement Milkomeda as a Layer 2 solution on Cardano at the time due to some technical obstacles.

Milkomeda A1 was a Layer 2 on Algorand. While a sidechain gives you greater flexibility but less security, a Layer 2 gives you full security with mathematical proofs, but less flexibility as you need to program everything in zero-knowledge (ZK) circuits. Unfortunately Milkomeda was discontinued as it was not attracting enough liquidity to generate sufficient transaction fees. It has provided many learning points for projects that followed. 

Other interoperability solutions 

There is a growing list of builders on Cardano. For example, Wanchain is a bi-directional decentralized, non-custodial cross-chain bridge linking Cardano to other tier 1 blockchains. It opens up access for Cardano users to assets like USDT, USDC stablecoins and wrapped BTC. As well as being a decentralized interoperability solution, Wanchain is layer 1 proof-of-stake (PoS) blockchain with an Ethereum-like ecosystem that supports industry-standard Ethereum tools, dApps, and protocols. It has certain similarities to Cardano. Wanchain employs the Galaxy Consensus PoS consensus method, which employs several cryptographic approaches, such as distributed secret sharing and threshold signatures, to enhance random number generation and block creation processes. Galaxy Consensus is a continuation of Cardano’s own Ouroboros protocol.

Another noteworthy project to observe is the Rosen Bridge, which interconnects Ergo, Cardano, and Bitcoin. Their roadmap shows plans to add support for more EVM-based chains, DOGE, among others. 
Entering the Cosmos
The Cardano Foundation introduced Inter-Blockchain Communication Protocol (IBC) capabilities to Cardano in 2024. The IBC protocol works in a similar way to the ubiquitous TCP/IP backbone protocol which the internet runs on. IBC is like a universal framework for blockchains to talk to each other, not unlike how TCP/IP facilitates seamless communication between computers. 

This allows for data and asset transfers with 115 interconnected blockchains, some of which have prioritised other elements of the blockchain trilemma. They can benefit by piggybacking on the proven security, 100% uptime and deterministic fees Cardano has demonstrated since 2017. 

Projects can now bridge between Cardano and Cosmos SDK-based sidechains. IBC also affords Cardano a new avenue to connect with Ethereum Virtual Machine (EVM)-based sidechains.  

The CF is working on an Aiken-based Tendermint Light Client, as well as implementing IBC primitives. Several frameworks provided by the Cardano developer community will be involved, including Pallas, lucid-evolution, Ogmios, Kupo, and db-sync. Mithril will also be leveraged for threshold-based signatures and state proofs necessary for a native IBC connection.

The CF engineering team continues to actively develop and improve the security and efficiency of this solution with help from the developer community. The general security model of IBC is built around Light Clients, whereby chain A generates a proof of its state that is then verified on chain B. This can then be used to check if a token has been locked or burned on chain A, so that it could be released on chain B without the need to fully follow each chain connected to Cardano via IBC, and vice versa. This functionality is also at the root of the bridge to Bitcoin, as proposed by BitcoinOS. 


These capabilities offer exciting potential for Light Clients in general. Users have more sovereignty and less trust assumptions compared to how light wallets typically work today, where you typically communicate with a backend that tracks the chain for you, but it is also less heavy weight than a full node wallet like Daedalus.

Layer 2 solutions

There are generally 3 types of Layer 2 solutions.

State Channels (like Hydra, or the Lightning Network on Bitcoin)
ZK Rollups
Optimistic Rollups  

Both ZK and optimistic rollups collect off-chain transactions into a batch, then submit them to the Layer 1 blockchain as one transaction.

A Zero-knowledge (ZK) rollup is built on top of the existing Layer 1 blockchain to make the transactions faster, cheaper, scalable, secure, and private by not disclosing everything while transacting with the verifier. The problem with many other Layer 2 solutions is that they are not secure enough. There is a trade-off where they focus more on scalability, which can leave them open to exploits. ZK rollups are so powerful as it’s much faster to prove you know the answer, rather than doing the computing to get the answer. 

Optimistic rollups offer greater flexibility than ZK Roll-Ups because they don’t require everything to be encoded in a ZK circuit. As the name suggests, you optimistically presume transactions are valid, or use fraud proofs to prove false transactions later. The trade off is that there is a delay caused by the challenge period (that allows monitors to submit fraud proofs).

ZK rollups are more scalable as they consume less blockchain resources compared to Optimistic rollups. ZK rollups are difficult to implement today, mainly because they take time to compile and can slow down your dApp. This is improving every year, however, and it is a hot research space. 

Ethereum has a huge focus on ZK roll-ups with many projects trying to dominate. @StakeWithPride pointed out some dubious design fundamentals and values coming out of the Ethereum community. In a video from a core developer, there is an admission that a serious hack is likely with ZK roll-ups on Ethereum. The proposed solution is to leverage Intel SGX trusted enclaves to ensure security, which doesn’t sound very decentralized.

On Cardano, there was already the unsuccessful Orbis ZK project funded by Catalyst. Dr Markulf Kohlweiss announced the ZK Lab at Edinburgh University and dcSpark have marked ZK research as a priority, having contributed to this space already with their paper on Sonic: Zero Knowledge SNARKS.

April 20, 2022, ‘4/20 Hangout with Charles’ Twitter space,


Re: L2 scaling solutions, ZK roll ups… CH:

Why do we care about this technology? Why is this useful to me as a consumer? Ok, let’s say you go to a bar, and you get carded. When you show your driver’s license to the bartender, you reveal more than just your age. You reveal your precise age. Oftentimes, the driver’s license has an address on it. If you’re an organ donor or not, a picture of you, your gender, you reveal some of them... I think they put Social Security numbers on the driver’s license, military ID, and even more, a passport. You get all this stuff that the bartender should not know.

The bartender is looking for a threshold condition. Are you above or below the drinking age? That’s all they need, it’s a Boolean yes or no. Are you over 21?... at or over 21? So, what a zero-knowledge proof can do is, for an identity system with digital ID, you can prove to that bartender that you’re over at the age of 21, but reveal nothing else about you. No other metadata, and an abstraction you can do that for any challenge response protocol. Are you a US citizen or not? Is the money that I've received taxed or not? Are you fully compliant with laws in the state of Colorado? or not? Yes or no. These types of things. Are you eligible to see this information? Yes or no. You remove that judgment in that respect. 

Now the other application is, do you own this money or not? Zero knowledge proofs are perfect for this application, because basically you’re proving that the money exists and that you have the right to spend it, but you’re not revealing which money it is, and you’re not revealing who you are. So that’s why they’re used in privacy systems.

Zero Knowledge of what might happen

Achieving direct interoperability with (EVM) Ethereum Virtual Machine-based chains is not trivial to implement securely. EVM and similar programming paradigms built around a global mutable state are a vector for bugs, exploits and hacks.

Perhaps the scaling solution with the most potential has just emerged recently with the cryptographic primitives introduced by the Chang and Plomin hard forks. Many feel the best way to achieve interoperability is via Zero Knowledge solutions. Now that ZK primitives are available only in the last few months, ZK verifiers can be implemented in Plutus. This offers safer interoperability from EVM-based chains that have symmetric provers. In addition, generating ZK proofs of Plutus scripts enables interoperability in the opposite direction, to EVM-based chains that have compatible verifiers.

With the recent Plutus additions, it has become possible to verify ZK proofs but the path to have Cardano produce ZK-based state proofs of itself is in the works at time of writing. 

While Ethereum’s vibrant Layer 2 scene has flourished over the past few years, Cardano's deterministic transaction model may offer a significant advantage for ZK Rollups. Whereas Ethereum’s transaction outcomes depend on the global state at the time of execution, Cardano's UTxO model ensures predictable outputs during transaction construction off-chain. The strengths of the UTxO model in Layer 1 bubble up to Layer 2. This means a world without the need for sequencers in ZK Rollups, promoting decentralization and potentially removing the reliance on external data availability layers. 

Even without the requirement for centralized sequencers and transaction batching, we still need to relay the state of Layer 2 to Layer 1 to guarantee system integrity and consistency. While Cardano doesn’t need sequencers to achieve determinism, Layer 2 still inherits its security from Layer 1.  UTxO’s deterministic behavior means new implementation possibilities. It should now be possible to develop decentralised ZK Rollups more efficiently than what we’ve seen to date with Ethereum’s roll ups.

So the design decisions taken in the beginning have consequences when scaling chains. Cardano focused on transaction determinism, local state and security which are essential ingredients for implementing ZK Roll Ups smoothly. Vast levels of venture capital funding has been pumped into the Ethereum ZK Roll Up ecosystem, however, most rely on centralized sequencers acting as glorified multi-sigs, many of which have been targeted in hacks and exploits. 

The strength and security of ZK Rollups rely heavily on the liveness and security of the underlying Layer 1, and no blockchain has a more impressive record in this regard than Cardano. Second only to Bitcoin in uninterrupted uptime since 2017, Cardano is the most stable and reliable chain offering smart contract capability. 

On Sunday, September 1, 2024, the Chang hard fork introduced advanced cryptographic primitives, the building blocks for ZK Roll Ups. There are several projects working on new Zero Knowledge solutions. Midgard is one example, which differentiates itself from existing Layer 2 solutions, with no reliance on centralized systems, operating without a centralized sequencer, custodial requirements, or multi-signature dependencies. It is not just a Layer 2 Roll Up in its own right, but a framework for building other Layer 2 solutions. 

An early success story in implementing ZK on "mainnet" was a repo from Modulo-P implementing verification of  widely used Groth-16 proofs. Although relatively late to the ZK Roll Up space, Cardano’s eUTxO model is more suited to support truly decentralized, trustless and performant Roll Up solutions in ways not possible on other chains. As Cardano’s fledgling ZK Roll up ecosystem starts to flourish, the foresight of earlier decisions will become more apparent. 
Midnight in the Garden of Good and Evil

At ScotFest (2022), Charles Hoskinson revealed his team had been working on another cryptocurrency for the past four years. It is called Midnight and will be a Cardano sidechain with a native token called dust. As mentioned before, the way sidechains work on Cardano is as a partnership. Midnight gains decentralization, security, infrastructure, liquidity and a thriving ecosystem from Cardano. In return, Midnight pays rent in the form of rewards to Cardano SPOs and delegators. 

IOG reviewed existing privacy solutions like Monero and Zcash and felt they could do better. Research on the privacy requirements for smart contracts has been ongoing for some time.  Kachina-Foundations of Private Smart Contracts is a paper Charles Hoskinson ranks as ‘one of our most forward-thinking publications’.

IOGs brains thrust (the likes of zero knowledge expert Dr Markulf Kohlweiss) went to work and reviewed other solutions like Zexe and concluded that three ‘must have’ properties were absent in the blockchain space today. Abbreviated to ‘ACE’, they are: freedom of Association, freedom of Commerce and freedom of Expression. 

These basic human rights are not always present in some jurisdictions for various reasons. Midnight will offer confidentiality and privacy with the ability to freely associate with people and engage in legitimate commercial transactions. 

There is also the regulatory side. It is not illegal to seek confidentiality and privacy in most circumstances. As many people believe crypto is cloaked in secrecy and only used for nefarious activity, new dApps need to protect user rights and wishes, but also enable them to comply with regulatory requirements. dApps on Midnight enable users to protect their own data, to keep their data in their own systems. They don't have to share everything but can share assertions about their personal data based on things like KYC and AML, and the body on the other side of the transaction can trust that those assertions are correct. Selective disclosure is not the same as a ‘back door’, fake news and FUD has already been called out and corrected on this matter. 

Midnight goes beyond just privacy transactions and attempts to support true confidentiality with private smart contracts. To implement this concept, certain data must be private to the public, but still enable voluntary or involuntary disclosures. This can be applied in many use cases. With 2024 being the year of elections globally, consider how decentralized anonymous voting could work on Midnight. Eliminating the risk of vote tampering, a Dapp could leverage zero-knowledge cryptography to enable voters to register and prove they are eligible without disclosing unnecessary personal information. A similar use case would be for sharing patients medical records. The implications are far-reaching and profound. 

Monero and Zcash are proven solutions for keeping your transactions and tokens private, but programmability is required too. The Kachina paper explores how to write private smart contracts, and IOG has been busy bringing the theory to life. 



Figure 9.4: Why Midnight stands out, from IOG’s Chief Strategy Officer Rob Adams talk at ScotFest

After many years of research and development, they created a virtual machine in Typescript. This is significant in terms of developer adoption. Typescript (~35%), a superset of JavaScript (65%), is one of the most popular programming languages in the world. For perspective, Haskell adoption languishes somewhere between (1-2%). Taking some of the learnings from Plutus, which only arrived years after Cardano’s launch, Midnight adopted a developer-first approach from day one. 

With regulation on the industry’s doorstep, Midnight looks like an astute strategic move by IOG. Regulators have a daunting task trying to legislate for a nascent industry with emerging technology sometimes not yet in production. Midnight offers a potential middle ground where core principles of crypto can be upheld, but also enables dApps to meet compliance requirements in different locales. 

Just one example is when a large global enterprise needs to comply with GDPR requirements in Europe, but still have a different US version to comply with requirements in the Bank Secrecy Act. Most companies face large penalties if they fail to keep user data private. There are many other obvious use cases from making medical data accessible, to enabling underground newspapers in volatile societies to operate.

Charles Hoskinson mentioned in his 2022 New Year’s Eve twitter space sidechains will be rolled out based on the Japanese martial arts concept of Shuhari …you learn, you do, then you teach. IOG ‘learned’ with the Mamba proof of concept, now they will ‘do’ with Midnight and ‘teach’ with various toolkits, blogs and formal papers. 

Throughout 2023, the Cardano community craved more details about this new, mysterious Midnight. A long-awaited strategy update was delivered at the Cardano Summit 2023. Despite a keynote with the trademark whiteboard, there was still some confusion about the details. Chinese whispers led to FUD suggesting IOG was abandoning Cardano for Midnight, and that Midnight didn’t need Cardano to succeed.

Midnight Special

As time was tight on stage in Dubai, Hoskinson promised a new whiteboard video to clarify any gray areas. The follow up Midnight Special was comprehensive. There had been talk for some time about renaming sidechains to something more descriptive. Partner Chains would be the new model for interoperability on Cardano as it suggests each Partner benefits from the relationship. 

The new model would mean there would still be separation of layers, but now the Cardano Settlement Layer (CSL) would be renamed as the Cardano Asset and Settlement Layer (CASL). Its purpose and functionality would remain largely the same, ie. act as a proven, robust settlement layer for partner chains. The Cardano Computation Layers (CCL) would now be known as Cardano Service Layers (CSL) mirroring the philosophy of microservices, or service oriented architecture. Partner Chains, like Midnight, would have the flexibility to build their own computation layers using modular frameworks and existing components while still leveraging the CASL. Each (CSL) service layer might have its own distinct logic with unique tokenomics, consensus protocol, etc, however they will have the same ‘common ancestor’ in the CASL. 

Figure 9.5:  The new partner chains model, graphic credit: cexplorer
Hoskinson explained they had learnt a lot from ScoreX, Mamba, Cosmos and more recently Polkadot’s Parity Substrate stack when devising Midnight’s architecture. Substrate is a proven open-source framework tried and tested on 100 Polkadot Parachains. It describes itself as a ‘Blockchain Framework for a Multichain Future’. Hoskinson went on to explain Midnight would use Substrate as a starting point, and would develop their own custom ‘pallet’ components. 

And it's an open source project at the end of the rainbow too. And what's nice is we got kind of a huge leapfrog with getting Parity Substrate as a starting point, but it's really important to understand it’s not stock Parity Substrate. There’s going to be a humongous amount of upgrades, modifications and additions.


For example, the Cardano network stack is being ported over…it's written in Rust, and so it's not ‘stock Parity network’…we spent tens of millions of dollars building the best network stack in the world for cryptocurrency. We would be bloody insane to throw that away for our partner team framework. Brand new consensus protocols are being developed, and then run in this setting with Minotaur, and there's a lot of magic there…so that's all new code and you know, different ways of doing pallets, so all kinds of stuff. 


So there's a big deviation from what Substrate brought to the table, but then there’s an acknowledgement that there was a lot of amazing engineering work that the Polkadot community did ...they have 190 parachains that they tested it on. So it makes absolutely no sense to throw all that work away…  It's just hybridizing that and keeping the best parts and blending them…and frankly that's what we should be doing, as an industry… is that everybody's doing good work, let's stop fighting each other, let's acknowledge it and the highest compliment is not a tweet saying you're doing good work… the highest compliment is taking the code and building on top of that code, that's what open source truly means at its core.


Borrowing ideas and benefiting from others research is nothing new in the blockchain space, despite the rivalries and tribalism. For example, Polkadot’s BABE protocol took inspiration from Ouroboros Praos. 

Adopting a multi chain strategy with Substrate and leveraging the findings from the Minotaur paper, Midnight will be able to leverage multiple consensus protocols. We are entering uncharted waters now as Cardano can potentially be the settlement layer for more chains. Security will be provided by Cardano’s SPOs as before, but now Minotaur will allow validators from other chains to contribute. The introduction of Babel fees will smooth integration as chains can transact in their own native currency, while still allowing Cardano SPOs to be compensated in ada. 

Midnight CEO Eran Barak gave more detail,  explaining Midnight will be a 4th generation blockchain as it enables data protection and a multi-resource consensus model. Advancements in zero knowledge technology enabled with the Change and Plomin hard forks now allow data and metadata to be protected. 

Jargon clarified


With so many new acronyms and announcements, Hoskinson clarified

There's two projects at the same time, Cardano partner chain toolkit and Midnight. One is downstream of the other …Midnight is downstream of the partner chain toolkit, and there's a separate team that works on that… they're both in Rust, with heavy modifications, but one is a blockchain builder kit, and its intention is to build out the partner chain ecosystem and the other is specifically Midnight’

As we started the chapter talking about Layer 1s, Layer 2s, state channels and sidechains…it can all get a bit confusing as to where a partner chain begins and ends. Hoskinson added further clarity:

So 'cause I often get asked a question ‘is Midnight a layer 2 or a sidechain?’ …I say it's neither and both…it’s neither in that it does not rely solely on the security of the main chain, for its security, and it doesn't rely on itself for its security. It actually borrows from both, and you can run multiple consensus algorithms at the same time. So ideally I'd like to blend useful proof of work on Midnight with a BFT protocol enabled by the stake pool operators of Cardano. And how do all of those pieces come together? …that's why I say there's kind of three parts. There's a Cardano part, there’s a framework part and then there’s a Midnight-specific part… and that’s going to take a little while to sort it’s way out.

But the other cool thing is that these things always benefit each other. So when we talk about Input Endorsers, a lot of the ideas that we're learning from partner chains are kind of being taken for a test drive, that could then be applied with the design of Input Endorsers and the long term sharding and scalability of Cardano's main chain. So when these SPOs are running this, we're learning a lot that can then be used to actually run and accelerate Cardano transactions and basically make our network have a much higher native TPS rate, and so it's all interconnected in in that respect

The Partner Chains strategy seems to be betting on arguably the most successful features of Cardano to date, its consensus and staking mechanism and the implementation of Minotaur being a game changer. Unlike any of the popular cloud service providers, Cardano has never been down since its first block was minted in 2017. Its liquid, non-custodial staking mechanism is years ahead of its time. Ethereum has paid Cardano a back-handed compliment by finally moving to proof of stake, subsequently proposing liquid staking and now even Haskellers are welcome to use Yolc - a Haskell-powered, safe, expressive, fun language for Ethereum.  Hoskinson describes the Minotaur paper as ‘probably the best thing we've ever written in the history of our company… because this ends the fight forever about interoperability’.

IO’s initial Partner Chains toolkit release came in August 2024. The benefits for prospective partners is similar to the IBC bridge: 

security, 
liquidity from stake protocol powered by 3,000 Stake pools
faster bootstrapping for a new ecosystem with existing developer base
flexibility to implement mixed consensus protocols and validator committee structure
ability transition to layer 1 status, without any lock-in with Cardano

Midnight is to be the first such partner chain to launch with this model. The Chang and Plomin hard forks introduce the required Zero Knowledge (ZK) primitives required for many projects, including Midnight. Midnight will leverage ZK Snarks to distinguish between an dApp’s public and private data, so sensitive data never leaves your device. Advancing further on Cardano’s capabilities, Midnight will feature shielded and unshielded data primitives so for the first time a blockchain can support selective disclosure. Learning from some of the drawbacks with Ethereum’s Layer 2 ecosystem, Midnight will not be a parasitic competitor to Cardano, rather complement it by bolstering its network and liquidity. It will introduce further connectivity with other chains like Ethereum, Bitcoin amongst others. 

There is precedent for such partnerships in the cloud provider world. While Oracle dominated the on-premise database world for decades, they were late comers to the cloud world. They gained a foothold by partnering with Amazon Web Services and Microsoft Azure, to make their database available on rivals’ platforms. Each partner gains something, and end users benefit from less tribalism.

The Midnight whitepaper outlines a dual-token model. While unusual and not trivial to implement, this model already exists elsewhere, one example being Neo. The uncertainty around network costs and transaction fees can be an issue for users. Midnight will introduce two tokens, DUST and NIGHT, to separate governance and operator incentives from user fees. 

Rewards to incentivize participation in governance, consensus and block production will be issued in an unshielded token called NIGHT. It won’t be used to pay for network usage, but can be transferred between addresses and traded on exchanges as a Cardano native asset.

The oil that greases the machine will be the DUST token, required if you want to use the network. It will serve a similar purpose to GAS on Ethereum, but crucially will have the option of hiding transaction details. What will be a novelty for most existing ada holders is that DUST will act as a shielded token which cannot be transferred between addresses. 

This dual-token model protects against coins being delisted on exchanges, as happened before with privacy coins like Monero. Unlike other privacy-based tokens, Midnight supports private transactions but also identity management and selective disclosure. 

The white paper describes NIGHT as a deflationary token, while DUST will be earned proportionally based on how many NIGHT tokens you hold. NIGHT holders can then, in theory, use the network for ‘free’ but the game theory and incentives will need to prove themself in practice. 

The Midnight devnet and testnet were met with overwhelming interest and participation from hundreds of projects. Compact, a new smart contract programming language, based on Typescript, has been well received. There was a buzz of anticipation in the air at the Lisbon kickoff event, which took place during the week of the biggest tech conference in the world Web Summit. A glossy marketing video was unveiled indicating a welcome new approach to marketing and engagement. Everyone in the Cardano community is looking forward to the rollout of the remaining roadmap items in 2025.




Figure 9.6: Midnight roadmap
