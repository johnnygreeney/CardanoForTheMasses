# Chapter 5: Goguen (Smart Contracts)

*‘The most damaging phrase in the language is... it’s always been done this way’* <br>― Grace Hopper

<br><br><br><br><br><br>

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/eutxo5.png "eutxo tweet") 

## Extended UTXO 

Blockchain networks are complicated data structures. Transactions traverse the chain on a regular basis, leaving digital fingerprints[^01] that must be carefully tracked and managed to maintain the underlying ledger’s integrity and trustworthiness. In the blockchain world, there are two main types of accounting ledgers: UTXO-based blockchains (like Bitcoin) and Account/Balance chains (Ethereum, and others).

The accounting models of these two models vary in many ways. The Unspent Transaction Output (UTXO) model is used by Bitcoin, Cardano, Zcash, Ergo, Avalanche and others while the Account/Balance model is used by Ethereum, Polkdot, Algorand, etc.

Cardano aimed to create an Extended UTXO (eUTXO) accounting model by combining Bitcoin’s UTXO model with Ethereum’s capacity to handle smart contracts. The adoption of eUTXO makes it easier to integrate smart contracts into the Cardano network.

**How does the accounting model work?**

The analogy of a balance sheet is often used to explain the account model. A balance sheet is required by any commercial entity to maintain an accurate record of profit, loss, cash flow, and other factors. Companies can visualize their financial situation at any moment in time by keeping meticulous records of all this information. Another benefit of a company’s accounting ledger is the ability to track the origins and ownership of funds. Blockchain networks also need an accounting model to establish who owns what currencies, monitor where those coins move, which ones are used up, and which ones are still accessible for spending.

**Account/Balance model vs. UTXO model**

Accountants used to maintain records of the transfer of funds in physical ledger books with handwritten entries. Electronic versions of the same thing are being used by businesses. To monitor provenance and ownership, blockchains employ transactions as records (much like entries in a ledger book). These transactions include a lot of information (where the coins came from, where they’re going, and how much change is left over).

**UTXO**

An unspent transaction output (UTXO) is the term for the amount of digital currency that remains after a transaction. The flow of assets is documented in a UTXO model as a directed acyclic graph[^02] with nodes representing transactions and edges representing transaction outputs, with each successive transaction consuming some UTXOs and adding new ones. Users’ wallets determine the users’ balance by keeping track of a list of unspent outputs connected with all addresses held by the user.

In many respects, UTXO is identical to currency. ‘Cash in cash out’ is the commonly used analogy. Let’s say you have to pay a restaurant bill of €15. You forgot your credit card so pay in cash. You pay with a €20 note (input) and want to leave a €2 tip. The waitress puts €15 in the till (output 1) and gives you back a €2 coin (output 2) and a €1 coin (output 3). She puts the €2 tip (output 4) in the tip jar. Regardless, if you decide to leave a tip or not, or give exact change, the inputs and outputs must match.

The same is true for UTXOs. Any balance you have in your blockchain wallet may be built up using a variety of UTXO combinations depending on prior transactions, but the total value stays the same. In other words, a wallet address’s balance is the total of all unspent UTXOs from prior transactions.

**Concept of ‘change’ in UTXO models**

UTXOs introduce ‘change,’ much like currency transactions at a shop. You can’t cut a €50 note into smaller pieces to pay for anything that costs €15, for example, when you take it out of your pocket. You must hand over the whole €50 money and the clerk will give you your change. The same is true for UTXOs. A UTXO cannot be ‘split’ into smaller pieces. UTXOs are used in their entirety, with the remainder being returned to your wallet’s address in the form of a smaller UTXO.

**UTXO advantages**   

One can derive reliable information regarding the blockchain’s use and financial activities by examining and tracking the size, age, and number of UTXOs being moved around.

Other benefits of UTXO models may be found like better scalability, especially for state channels and sharding solutions. On privacy, UTXO makes it difficult for a malicious actor to link transactions. A user can constantly change their receiving address, with new addresses having no previous owner. Also, since each UTXO may only be consumed once and in its whole, the transaction logic is streamlined, making transaction verification considerably easier.

To summarize UTXO:

- A UTXO is the result of a prior transaction that may be spent in the future
- There are no accounts in UTXO chains. Instead, coins are kept as a list of UTXOs, and transactions are made by consuming existing UTXOs and creating new ones in their place
- Balance is the total number of UTXOs possessed by a certain address (UTXOs are used whole).

The **Account/Balance model** is a method for keeping track of, and balancing, your finances. An account (which may be managed by a private key or a smart contract) is used to keep a coin balance in blockchain models that employ an Account/Balance accounting model, as the name implies. Assets are represented as balances inside users’ accounts, and the balances are saved as a global state of accounts maintained by each node and updated with each transaction.

Account/Balance chains (such as Ethereum) function similarly to regular bank accounts in many ways. When coins are deposited, the wallet’s balance rises, and when coins are moved elsewhere, the wallet’s balance falls. The key distinction is that, unlike UTXOs, you may only utilize a portion of your balance. So, if you have 50 ETH in your account, you may transmit a piece of it to someone else (for example, 15 ETH). As a consequence, your account balance will be 35 ETH, and the address to which you delivered the coins will be increased by 15 ETH. In Account/Balance accounting models, the idea of change does not apply as it does in UTXO accounting models.

Transaction sizes are generally smaller with the account model, compared to UTXO, as only basic data regarding sender, receiver, amount and signatures are captured. Onboarding new nodes is therefore easier as there is less data to sync. 

To summarize the Account/Balance concept: 

- This accounting approach works similarly to how a bank does 
- Users have accounts that keep their coin balances 
- Partial balances may be spent
- The idea of change is irrelevant
- Account models are suited for Layer 2 deployments as transaction size/metadata is light.

**Transactions Outputs and Inputs**

The word ‘transaction’ frequently conjures up images of money. While this definition applies to Bitcoin (since the Bitcoin is used to transfer payments between peers), many other blockchains (like Cardano) are more flexible. The word ‘transaction’ is significantly more complicated in these circumstances. Transactions may be thought of as value transfers.
Each transaction in a blockchain system may have one or more inputs and one or more outputs. If one wishes to grasp how a transaction works and how it connects to UTXO, one must first comprehend the notion of inputs and outputs. Consider a transaction to be the operation that unlocks past outputs while also creating new ones.

**Transaction output**

An address (which you might view as a lock) and a value are included in the transaction output.[^03] In line with this analogy, the address’s signature is the key that unlocks the output. An output may be used as an input after it has been unlocked. New transactions use previous transactions’ outputs while also producing new outputs that may be consumed by subsequent transactions. Each UTXO may only be used once, and it must be consumed in its entirety. Only one input may spend each output.

**Transaction input**

The output of a preceding transaction is referred to as a transaction input. A pointer and a cryptographic signature that serves as the unlocking key are included in transaction inputs. The key unlocks a prior transaction output, and the pointer refers back to it. The blockchain labels an unlocked output as ‘spent’ when it is unlocked by an input. New inputs may then refer to new outputs produced by a given transaction, and the chain continues. The UTXOs are the new outputs (which have not yet been unlocked, i.e., spent). Unspent outputs are just that: outputs that haven’t been used yet.

**How UTXO works**

Transactions consume unspent outputs from earlier transactions and create fresh outputs that may be used as inputs for future transactions under a UTXO accounting model.

These UTXOs are managed by the users’ wallets, which also start transactions using the user’s UTXOs. At all times, every blockchain node keeps track of a subset of all UTXOs. This is called the UTXO set. In technical jargon, this is the chainstate, which is kept in each node’s data directory. The chainstate is changed whenever a new block is added to the chain. The list of recent transactions is included in this new block (including of course a record of spent UTXOs, and new ones created since the chainstate was last updated). Every node keeps a duplicate of the chainstate.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/51utxo.png "utxos")

**Figure 5.1**:  UTXOs

A UTxO consists of the reference to the transaction that created it (TxId), and its index (TxIx) on the host transaction. Think of the index as like a plane seat number, where the UTXO sits on the transaction. A UTxO is associated with an asset value, an address which dictates its spending conditions and other metadata. A transaction can take multiple inputs (consuming multiple UTxOs) and produce multiple outputs (new UTxOs to be used by future transactions). This is why measuring transactions per second is nonsense on Cardano, as a transaction can contain hundreds of inputs and outputs. We’ll revisit this topic in Chapter 8 (Basho).

As you continue reading about Cardano, you’ll see almost everything happens as a result of a transaction. A transaction is usually one of the following on-chain events:

- Transfer of ada
- Transfer of Native Assets
- Minting or burning of Native Assets
- Posting of delegation certificates on-chain
- Stakepool registrations 
- Metadata stored on-chain
- A governance upgrade proposal
- Any combination of the above

**Why Cardano chose eUTXO**

Cardano’s UTXO accounting mechanism is not the same as Bitcoin’s, since Cardano is meant to do more than only manage payments. The necessity for increased programming expressiveness in the Alonzo era’s smart contracts feature required a unique (’Extended’) approach.

The ‘basic’ UTXO concept has a restricted programmability expressiveness. With the establishment of an account-based ledger and related contract accounts, Ethereum’s Account/Balance accounting model addresses this particular challenge. However, the contract code’s semantics grew significantly more sophisticated as a result, which had the unintended consequence of compelling contract writers to fully comprehend the semantics to prevent the insertion of potentially extremely expensive flaws in the code.

An ‘extended’ UTXO solution would need two features that the current UTXO model lacks:

1. To be able to keep the contract in its current state.
2. To be able to ensure that the same contract code is used throughout the transaction sequence. This is what is referred to as continuity.

The eUTXO model has the advantage of being able to forecast the fees necessary for a successful transaction before it is processed. This is a characteristic that account-based models do not have.

**Why is it called eUTXO?**

Cardano’s UTXO accounting mechanism is not the same as Bitcoin’s, since Cardano is meant to do more than only manage payments. The necessity for increased programming expressiveness in the Alonzo era’s smart contracts feature required a unique (’Extended’) approach.

The ‘basic’ UTXO concept has a restricted programmability expressiveness. With the establishment of an account-based ledger and related contract accounts, Ethereum’s Account/Balance accounting model addresses this particular challenge. However, the contract code’s semantics grew significantly more sophisticated as a result, which had the unintended consequence of compelling contract writers to fully comprehend the semantics to prevent the insertion of potentially extremely expensive flaws in the code.

An ‘extended’ UTXO solution would need two features that the current UTXO model lacks:

1. To be able to keep the contract in its current state.
2. To be able to ensure that the same contract code is used throughout the transaction sequence. This is what is referred to as continuity.

The eUTXO model has the advantage of being able to forecast the fees necessary for a successful transaction before it is processed. This is a characteristic that account-based models do not have.

**Why is it called eUTXO?**

UTXO is ‘extended’ by allowing for extra ‘locks’ and ‘keys’ controlling under which conditions an output may be unlocked for consumption by a transaction (in addition to value), and by allowing for custom data to be added to outputs. In other words, rather than having public keys (hashes) for locks and accompanying signatures serve as ‘keys,’ eUTXO allows arbitrary logic to be implemented using scripts. This arbitrary logic examines the transaction and data to determine whether or not the transaction may use an input.

**What’s so great about eUTXO?**

Cardano’s ledger architecture extends on the UTXO model to accommodate multi-assets and smart contracts while maintaining the UTXO model’s benefits. Groundbreaking research allows Cardano to do functions that no other UTXO ledger can, making it a unique contender in the blockchain space.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/utxo52.png "utxos")

**Figure 5.2**:  UTXO model

**The extended UTXO model**

The UTXO model is extended in two ways by the eUTXO model:

1. The lock-and-key analogy is used to extend the idea of an ‘address.’ Addresses in the eUTXO model may include arbitrary logic in the form of scripts instead of confining locks to public keys and keys to signatures. When a node verifies a transaction, for example, it evaluates whether the transaction may utilize a certain output as an input. If the output can be used as an input, the transaction will look up the script supplied by the output’s address and run it.

2. The second distinction between UTXO and eUTXO is that, in addition to an address and a value, outputs may contain (virtually) any data. By enabling scripts to carry state, they become considerably more powerful.

Furthermore, eUTXO expands on the UTXO concept by enabling output addresses to include complicated logic to determine which transactions are allowed to unlock them, as well as by allowing custom data to be added to all outputs. When verifying an address,[^04] the script will look at the data carried by the output,[^05] the transaction being checked, and some extra data known as redeemers[^06] that the transaction supplies for each input. The script[^07] provides enough context to deliver a ‘yes’ or ‘no’ response, in what may be very complicated circumstances, by uncovering all of this information.[^08]

eUTXO allows for arbitrary logic to be expressed in the form of scripts. This arbitrary logic examines the transaction and data to determine whether or not the transaction may use an input.

The graph structure of the UTXO paradigm differs significantly from the account-based model employed by several current smart-contract enabled blockchains. As a consequence, design paradigms for dApps on account-based blockchains do not easily adapt to Cardano. Because the underlying representation of the data is different, new design patterns are required.

The per-branches architecture of the UTXO (Bitcoin) model is carried over to eUTXO, where one branch is defined as a series of transactions requiring a succession of validations. Building dApps and other solutions with numerous UTXOs is vital for splitting the functionality over various branches and enforcing additional parallelism.[^09] This has benefits when trying solve the scalability conundrum. More about Scalability in Chapter 8 (Basho).

**eUTXO Advantages**

Compared to other accounting models, the eUTXO model has several distinct benefits. The transaction’s success or failure is solely determined by the transaction and its inputs, not by anything else on the blockchain. As a result, before a transaction is posted to the blockchain, the legitimacy of the transaction may be confirmed off-chain. A transaction may still fail if another transaction consumes an input that the transaction is expecting at the same time, but if all inputs are still available, the transaction will succeed.

This contrasts with an account-based approach (such as Ethereum), which allows a transaction to fail in the middle of its execution. In eUTXO,[^10] this will never happen. Also, transaction execution costs may be calculated off-chain before transmission, which is something that Ethereum does not allow.

Cardano’s eUTXO paradigm provides a safe and flexible environment for processing many operations without causing system issues. This architecture provides superior scalability and privacy, as well as more straightforward transaction logic, since each UTXO can only be used once and in its entirety, making transaction verification considerably easier.

The eUTXO model has the advantage of being able to forecast the fees necessary for a successful transaction before it is posted. This is a feature that account-based models do not have. Account-based blockchains, such as Ethereum, are indeterministic, meaning the impact of a transaction on the chain cannot be guaranteed. This ambiguity raises the danger of financial loss, unexpectedly expensive costs, and a broader attack vector for hackers to exploit. 

A deep technical analysis of eUTXO ledger’s architecture is beyond the scope of this book, however, you can get ‘into the weeds’ by reviewing IOG’s blog ‘Architecting dApps on the eUTXO Ledger’[^11] where they provide a sample architecture. SundaeSwap[^12] and Axo (previously Maladex) also blogged about their solution while *Spectrum Finance* (formerly known as ERGOdex)[^13] talked about their philosophy on *Cardano with Paul*[^14] YouTube channel. There are also some code samples from IOG on avoiding concurrency using multi signatures in the Lobster Challenge.[^15] IOG analyze a sample order book pattern[^16] architecture in their blog. For a deeper dive into eUTXO, read the handbook.[^17]

## ’Neither smart nor a contract’

While Vitalik Buterin and others[^18] have opined that smart contracts are neither smart nor a contract, let’s not be pedantic for the sake of brevity. A smart contract is a code-based automatic digital agreement that records, validates, and executes the contract’s binding transactions between numerous participants. When preset criteria are satisfied, the smart contract code automatically executes the contract’s transactions. A smart contract is just a brief program whose inputs and outputs are blockchain transactions.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/vitalik.png "Vitalik")

Smart contracts are self-executing and dependable, requiring no third-party intervention or presence. The smart contract code is kept on a decentralized blockchain network and spread throughout it, making it transparent and irrevocable.

Smart contracts are immutable because they cannot be modified, they are distributable and tamper-proof, they are quick and cost efficient because there is no middleman, saving money and time, and they are secure because they are encrypted.

**Why smart contracts?** 

Intermediaries are engaged in many commercial procedures that include the exchange of value (such as money, property, or shares) to ensure that the conditions of the agreements are comprehensive, clear, and met before the exchange may take place. The cost of a transaction is increased by these middlemen. Smart contracts have evolved as a technique of decreasing the time, third-party participation, and expense of reliably executing an agreement.

Smart contracts are software programs that are stored on the blockchain in an immutable format. They’re run on virtual computers, and their data is stored in the same immutable architecture. Businesses aiming to improve their operations might profit greatly from smart contracts. Many sectors, including automotive, supply chain, real estate, and healthcare, are investing in research to see how this technology might help them compete more effectively.

## Metadata on Cardano

**The need for metadata**

Remember, money is a social construct. It is only valuable if people acknowledge and believe in it. Most transactions have a context that needs to be captured in metadata. Bitcoin and its contemporaries have abandoned the requirement for reliable identities, information, and reputation in commercial transactions in their quest to anonymize and disintermediate central players. Adopting centralized methods to add this data loses the auditability, global availability, and immutability that is the whole idea of using a blockchain.

Transactional information is abundant in legacy financial systems such as those based on SWIFT. Regulation often involves attribution of individuals engaged, compliance information, reporting suspicious behavior, and other records and activities in addition to knowing how much value transferred between accounts. The metadata might be more essential than the transaction itself in certain instances. The metadata is the story of the transaction.

As a result, it appears logical to conclude that tampering with metadata may be just as dangerous as counterfeiting money or changing transaction history. Making no allowances for actors who want to freely participate in these domains seems to be detrimental to mainstream acceptance and consumer protection.

Adding metadata to transactions was the first step in preparing Cardano for DeFi. Cardano evolved into a smart contract platform with the launch of Goguen. This began by including metadata — information about the data being processed – in transactions, which was introduced to the blockchain. Cardano has evolved from a transaction-focused platform to a utility platform available to partnerships, businesses, and commercial applications that may be used for the complex processes that will characterize the decentralized financial future (DeFi).

With the growing number of cryptocurrency transactions, having access to immutable data that cannot be changed is critical. The Cardano blockchain keeps permanent records of completed transactions, guaranteeing a transparent and auditable history of financial activity. However, to give financial operations greater responsibility and visibility, context must be given to these transactions. Facts such as sender and recipient information, processing circumstances, and processing time are examples of additional information. This is accomplished by including transaction metadata.

**Data about data**

The term ‘metadata’ refers to information about information. It defines the context, content, and structure of records, in other words. Metadata promotes confidence through permanent data attestation, since blockchain technology offers a transparent ledger for preserving information immutably and securely.

Whether it’s a purchase for a product or service or a money transfer to a family member, all transactions have a definite purpose. When making an online purchase, for example, there is a lot of information that can be gathered about the transaction. Metadata may help convey the tale of a product purchase by revealing information about the customer and seller, the date of the transaction, the product maker, and the supply circumstances. 

**March 31, 2019. On metadata.** CH:[^19]

> An example of this…. let’s say that Bob goes to an ATM and withdraws $300 of value out of an ATM …now that’s a transaction …now let’s say Bob did that next in an Italian restaurant on his birthday and all of his friends happen to be there …you would say ‘oh it looks like Bob’s pulling money out to pay the check’ ….or in some way is connected to this event, he’s at a celebration, there’s people there… it’s expensive and let’s say it’s at 12 o’clock …it’s lunchtime… Bob can then go take 300 dollars from an ATM, so the same type of transaction but now I’ve changed the metadata…
> 
>Let’s say it's 2:00 a.m. right next to a known brothel ….so basically the exact same type of transaction …the same type of value, the same actor involved… this is his account and his money, but because you’ve changed the metadata it has vastly different implications… So, what if you could swap these metadata and then suddenly you can now make the Italian restaurant look like a brothel? …whoever controls that story has a lot of power.

With the advent of Bitcoin, developers began using blockchain technology to add small amounts of new data to the chain, knowing that the data would be accessible for the rest of time. In 2015, the University of Nicosia[^20] became the first university to issue academic certificates whose authenticity could be verified through the Bitcoin blockchain. Adding information to the chain became the norm over time. 

**Transaction metadata**

Metadata is a useful tool for certifying and validating information. It lets cryptocurrency assets save information about their previous owners, transfers, and values. This is especially useful when dealing with non-fungible[^21] assets that reflect value, such as property or intellectual property. A public key may also be used to sign and certify a variety of documents, proving the document’s authenticity.

One of the most well-known applications of metadata is in the supply chain. Factories, customers, suppliers, and delivery services are all part of the supply chain. Participants must give proof of interconnected services that are available to everyone for verification in order to allow effective data tracking. In this situation, metadata may give a full view of supply chain activities by combining fixed data on the blockchain ledger with metadata. For all parties, this ensures openness, immutability, and confidence.

**Atala**

IOG’s Atala product suite, which includes Atala PRISM, Atala Trace, and Atala Scan solutions, saw early commercialization of metadata deployment on Cardano. The IOG team is developing metadata support while connecting with the Cardano ledger to improve the entire product functionality in terms of data feasibility, accountability, and traceability.

Atala PRISM[^22] is a decentralized identification system that allows individuals to control their personal data and communicate with organizations in a seamless, private, and safe manner. On Cardano, the Atala PRISM team is using metadata to certify and store DIDs and DID documents. It will also be able to cancel credentials such as university certificates, in addition to creating them.

Atala Trace and Atala Scan are being developed to help brand owners get a better understanding of supply chain operations while also establishing product provenance and auditability. Metadata integration will be employed in these circumstances to store tamper-proof supply-chain information.

Transaction metadata was an early component of Goguen utility and smart contract capability, which were expanded and developed by a variety of additional features.

**Cardano Foundation partnerships** 

In line with their open source strategy, the Cardano Foundation leveraged Ledger Sync[^23] and the Identity Wallet[^24] to deliver the Bolnisi track and trace solution.[^25] The Bolnisi winemakers have already tracked 100,000 bottles of wine on Cardano. This project sets a precedent for future work, leveraging Web3 technology to verify a product's proof of origin and authenticity. This solution is reproducible for similar challenges with counterfeit goods across many industry verticals. 

I'ts no secret that the fashion industry loses billions each year from counterfeit products. The Cardano Foundation partnered with *Epoch Sports* and *Merchadise*[^26] to address the issue of licensed intellectual property. NFC chips linked to on-chain records on the Cardano blockchain verify the authenticity of their jerseys while also enabling more consumer engagement. The same solution is in place for the proof-of-concept (POC) hoodie in the Cardano store.[^27] The CF plans to publish all technical details on the Developer Portal in due course.

**Cardano’s metadata strategy**

Metadata has a wide range of applications. With this in mind, IOG has been trying to make it as simple as possible for developers to include metadata into their applications. IOG also want to ensure that ada holders have a simple means to see information about their transactions.

**Differentiators**

Metadata conveys a transaction’s narrative, and there are several methods to engage with it. Ada users may search for particular information in the Cardano Explorer, and developers can make use of metadata by embedding details directly into a transaction. The data may be directly contributed, or a Merkle tree[^28] of the data can be created and the root hash of the Merkle tree placed on the blockchain for larger data sets. Once this is completed, it can be shown that the data exists at a certain moment in time and that it is permanently stored on the chain for future use.

It’s also worth noting that transaction information is recorded on the blockchain and sent with every transaction. The fact that it is kept on-chain rather than in the ledger state is advantageous since it has no impact on transaction validation and does not degrade ledger performance.

The additional cost is that metadata increases the transaction’s size in bytes, and the processing speed is dependent on transaction size. The Concise Binary Object Representation (CBOR)[^29] and Concise Data Definition Language (CDDL)[^30] notations may be used to create metadata. Check the Cardano wallet’s transaction metadata and how to use transaction metadata schemes in Cardano CLI.[^31]

## Token Locking on Cardano 

Cardano’s growth has been envisioned as a journey encompassing five overlapping development eras, each of which is supported by the Ouroboros consensus system. As Cardano developed, the protocol adapted as well, as new features and functionality were added to the platform. Upgrades need progressive modifications to the network protocol. 

**The introduction of token locking**

Token locking was the main feature of the second Goguen protocol upgrade *Allegra*. This was the next major update for Goguen, after the network integration of metadata.[^32]

This was a minor technical adjustment to the consensus process that had little effect on the ledger. It was crucial, though, since it prepared the platform for smart contracts and the production of Cardano-based assets (in addition to ada). It also supports voting, an essential piece of Voltaire (governance) functionality. 

Token locking is a method of locking the usage of a single token for a defined purpose (such as voting or running a smart contract). The assets that are tallied by the blockchain ledger are referred to as tokens. There was just ada before this, but many more custom tokens were able to utilize the Cardano platform since. In this scenario, locking means ‘reserving’ a particular quantity of tokens for a certain length of time so they can’t be sold for a profit.

**Token locking enable smart contracts**

Token locking is required to implement sophisticated smart contracts and certain circumstances, such as when completing a purchase. When someone gets into a contractual arrangement to sell a painting to an art gallery, the seller promises that the painting will not be sold to anyone else. In this scenario, the token might represent the painting, while the ‘promise’ represents the real token locking. If the painting is sold to a third party, the contract’s guarantee will be breached, and any penalties will apply. With the introduction of token locking and the use of ada coins as tokens, contract providers will have access to this exact capability. 

Those ada holders who participated in the Catalyst Fund2 voting process had to ‘freeze’ ada. This indicated their voting privileges, based on how much ada they had locked. It proved each person had a certain amount of votes and avoided the chance of votes being tallied twice. Individuals were unable to assign more votes than they had, vote on opposing proposals, or duplicate vote.

Following the implementation of token locking on the mainnet Cardano ledger, future hard forks included multi-asset and other smart contract features. These features leverage token locking as well, giving Cardano users a plethora of additional options. This paved the way for non-fungible (unique) tokens to be created on the Cardano blockchain.

Cardano has a safe, seamless route to frequent protocol changes, each of which adds new value and usefulness to the network while reducing interruption and risk, thanks to the innovative hard fork combinator.

## Native Tokens 

**Tokens on Bitcoin**

Protocols were built early in Bitcoin’s existence to enable users to issue assets that piggybacked on Bitcoin’s accounting system to monitor numerous currencies at the same time. The Bitcoin protocol does not support these protocols natively, but they were created through hacks. Light clients are forced to depend on trustworthy servers in the case of Bitcoin overlays like Colored Coins and Mastercoin (now Omni). Transaction fees must still be paid in bitcoins. These characteristics, together with the fact that transactions are approved via a single pipeline, render Bitcoin unsuitable for multi-asset accounting.

**Tokens on Ethereum**

In July of 2015, Ethereum was launched. Even though Bitcoin had been in existence for six years at the time, the cryptocurrency world was a nascent industry. When Ethereum first appeared on the scene, its schtick was smart contracts. This meant that third-party developers could create their own apps and run them on the Ethereum blockchain in a decentralized way. Ethereum outperformed Bitcoin in terms of marketability and adaptability.

On the Ethereum blockchain, smart contracts allowed for the creation of user-defined tokens. The ERC20[^33] standard allowed for the creation of fungible Ethereum tokens, whereas the ERC721[^34] framework allowed for the creation of unique, non-fungible tokens. However, since the Ethereum chain did not enable native token support, user defined Ethereum tokens (both fungible and non-fungible) had an inherent inefficiency: they required the construction and execution of custom code.

**What is Tokenization?**

Tokenization is the process of converting physical objects into digital assets. Tokenization replaces a non-sensitive data element for a sensitive data element. This non-sensitive equivalent is known as a token, and it has no intrinsic or exploitable value or meaning. 

Reduced transaction costs, transparency, higher liquidity, decentralization, and increased efficiency are just a few of the benefits. Tokenization is a very adaptable feature that may be used to achieve a variety of goals. Tokens[^35] are programmable; thus they may be made unique, which adds to their usefulness.

Tokens may, for example, be designed to provide holders access to unique material, personalized items, or even a voting right. It makes no difference what the aim of the voting process is. Finally, tokenizing the capacity to vote provides individuals the sense of being a part of something bigger than themselves, and that their opinions may be heard.

Financial goods and economic models may be created via tokenization. Collectibles, alternative investments, gift cards, sports betting, in-game assets, commodities, video clips of your favorite NBA star[^36] and a variety of other areas are all possible examples. This has the ability to link physical products, services, and activities to the virtual world.

**Tokenization on Cardano**

Goguen added a technique that handles tokenization natively. Rather than depending on smart contracts, the logic is based on the Cardano ledger. IOG created an efficient tokenization technique that is superior to the Ethereum blockchain’s ERC20 and ERC721 standards by following this approach.

On the Ethereum blockchain, user-defined tokens (both fungible ERC20 and non-fungible ERC721 tokens) are non-native, meaning that the underlying ledger does not directly support them. ERC20 and ERC721 tokens are fundamentally distinct from Ether, Ethereum’s native coin.

The Cardano approach to tokenization allows for the representation of custom assets on the blockchain without the use of smart contracts, as well as for those assets to behave similarly to the primary currency, ada, with the exception that: 

- native tokens, unlike ada, can be minted and destroyed; and 
- Ada is the only currency that can be used to pay fees, rewards, and deposits at present. This may change with the introduction of Babel Fees and tokens specific to different new sidechains. More about this later.

**Native tokens parlance**

In the crypto industry, the phrases ‘coin’ and ‘token’ are often interchangeable, and sometimes they aren’t. And, in other cases, the word ‘token’ is used to refer to all digital assets. Cardano’s tokenization strategy is as unique as the blockchain itself, therefore here’s a glossary to help you grasp the native tokens architecture.

- A token is defined as a representation of an asset kept on the Cardano blockchain 
- An asset is defined as anything that can be quantified 
- A token bundle is a representation of numerous tokens in Cardano
- Token logic that runs on the Cardano ledger rather than smart contracts is referred to as native.

**Native tokens on Cardano vs Ethereum**

Token code for both standards (ERC20 and ERC721) is copied and modified, rather than being part of the system itself, therefore Ethereum needs custom code for user-defined tokens to be supported on the chain. This adds a layer of complexity, expense (gas[^37] is required to pay for the execution of the code), and inefficiency. This is an inherent flaw in the Ethereum blockchain since it allows for human error. If coding best practices are not followed, dodgy custom code might bring problems that can result in significant financial loss. Software vulnerabilities contributed to the loss of $300m worth of ether in one especially memorable[^38] occurrence. Solana[^39] has been restarted several times and suffered an expensive Wormhole hack. Cardano seeks to avoid such debacles.

The native tokens framework in Cardano enables user-defined tokens natively, that is, without the requirement for special programming. Native tokens are a kind of accounting system that is inherently provided by the ledger. This eliminates the complicated, unpredictable and expensive aspects of tokenization on Ethereum.

Cardano is a kind of decentralized ledger. Typically, a distributed ledger can only track a single asset type when it is created (usually its own cryptocurrency). However, as the ledger gets more decentralized, the requirement and capability of monitoring different kinds of assets on the same infrastructure emerges, which is why blockchains need to handle numerous assets such as stablecoins, utility tokens,[^40] credential tokens, and security tokens. Native tokens, unlike ERC20, do not need extra event-handling logic or specific transfer costs to monitor transactions.

The accounting infrastructure established in the ledger model, initially intended for processing ada-only transactions, was extended to support transactions that employ many kinds of assets at the same time. Native tokens have the advantage of not requiring smart contracts to transmit their value and may be traded alongside other kinds of tokens. 

Security is another benefit of native coins over ERC20. ERC20 tokens have been shown to be subject to a variety of security problems that are well documented.[^41] This is because creating ERC20 tokens requires manual changes of the contract standard, which might lead to mistakes and flaws. Because the ledger manages the token logic, creating and transacting tokens natively eliminates this risk. Additionally, native tokens do not suffer the same overflow and underflow vulnerabilities as ERC20 tokens since Cardano’s scripting language does not employ fixed-size integers and the ledger itself (as opposed to the ERC20 user code) monitors token movement.

**Four Differentiators of Native Tokens on Cardano**

**Lightweight Architecture**

The native token architecture is constructed around token bundles and is based on a multi-asset ledger structure. A token bundle might include a mixture of ada and other tokens. Instead of ada, these token-containing structures are recorded as outputs on the ledger. The asset ID of each kind of token contains a hash reference to the token’s minting policy. The minting policy is only verified during the minting or burning process, and it is not maintained on the ledger, making this method very light.

The asset ID also captures the fungibility connection in a lightweight way: tokens with the same asset ID are fungible with one other, but not with tokens with different asset IDs. The asset ID of unique tokens is coupled with a quantity of precisely one.

Within a single token bundle and throughout the whole ledger, the asset ID identifies each kind of token. It also indicates the token’s position inside the token bundle’s internal two-level map structure. This underlying data structure makes it possible to express fungible and non-fungible tokens in the same way. It also allows the system a lot of flexibility in terms of the types of asset use cases that can be tokenized. It’s simple to represent, say, a collection of one-of-a-kind works of art covered by a single minting policy set by the artist.

When we examine how Ethereum’s ERC20 handles asset transfers between two contracts, the inherent simplicity of native tokens is underlined even more. Smart contract code is necessary in this scenario, which adds complexity, as well as possibility for mistake and expense. Because several kinds of tokens may be traded in a single transaction, the structure of token bundles allows for a more lightweight approach to asset transfer.

**Inexpensive**

Transferring any amount of tokens between two peers in an ERC20 token ecosystem necessitates the execution of a smart contract, which comes with an execution charge (gas). The transfer of assets (tokens, ada, custom currencies, and so on) in Cardano’s native multi-asset ecosystem does not need a smart contract and does not incur an execution cost.

**More Security, less custom code**

Native tokens have a lighter and less expensive design than Ethereum’s ERC20 and ERC721 protocols. These two elements, however, would be useless without a strong security layer to ensure the system’s integrity.

System integrity with native tokens is based on the ledger attribute of value preservation (that is, that the sum of all the inputs is equal to the sum of the outputs). Unlike user-defined smart contracts, all native token transfer logic is embedded in the ledger. This guarantees that the system behaves predictably and consistently, and it eliminates the need for users to master smart contracts, which can often be vulnerable to exploitation by hackers.

While the ledger ensures accounting accuracy, the minting and burning of tokens is governed by their user-defined minting policies. A minting policy is hash-linked to the tokens it covers indefinitely, and there is no way to modify it. This ensures that an issuer’s policy cannot be amended to enable the minting or burning of a token that was not permitted under the initial policy. The policy for each kind of token being minted is verified and must be met whenever a minting transaction is put to the ledger. Except for ada (Cardano has limited supply of 45m ada), every token in circulation must have a minting policy and must have been minted pursuant to that policy.

As a result, the policy is the only custom code necessary to alter tokens in Cardano. Because the policy hash is linked to the asset identification, there is no need for a global asset registry, making asset creation cheap and simple. The technology is still basic, light, and simple to operate.

**Simplicity**

Now that Goguen’s native tokens are implemented, the ledger treats all tokens in the same manner. To avoid ambiguity and any errors or flaws, a token may only be minted in one method. This streamlining of development via the use of a uniform methodology resulted in speedier development and a better overall development experience.

IOG has provided more detail on GitHub under native tokens and how they compare to ada and ERC20.[^42] There is also a native tokens explainer video.[^43] Momentum built steadily after the *Mary* and *Alonzo* upgrades, with developers realizing the benefits of deploying native tokens and NFTs on Cardano. *Cardano blockchain insights*[^44] report almost 4.5 million wallets, over 9.3 million native tokens, and more than 1,500+ projects deploying to Cardano as of January 2024.[^45]

## Multi-Asset Support (MAS)

**Single asset ledgers**

Single-asset ledgers are cryptocurrency ledgers that track just one kind of asset.

**Multi-Asset support**

When a blockchain, ledger, or cryptocurrency enables recording the transfer and ownership of several kinds of assets on its ledger, it is said to have multi-asset (MA) support. The native tokens feature in the Cardano ecosystem provides this capability.

This feature extends the accounting infrastructure specified in the ledger model, which was intended to handle ada-only transactions, to transactions that employ a variety of assets at the same time. Ada and a range of user-defined custom token types are among these assets.

**Native versus non-native** 

Some cryptocurrency ledgers have features that allow you to monitor the ownership and transfer of many types of assets. Native MA (multi-asset) support is the name given to this sort of MA support. The MA functionality of Cardano is built-in or ‘native’.

It is possible to monitor assets for which there is no ledger accounting support if a cryptocurrency platform has sufficiently sophisticated smart contract capabilities.

**Assets**

On the blockchain, an asset is an item that represents value. A digital asset like ada, a position, a certificate, or a number of products are all examples of these items.

The word asset might refer to one of two things:

- the identifier of a class of objects, such as ada or ‘johnCoin’; or
- an exact amount of a certain thing, eg. ‘10 lovelace’, ‘33 johnCoin’, ‘this book’ or ‘these jars of marmalade’

An asset ID is a combination of the policy ID and the asset name that uniquely identifies it. It’s worth noting that, although ada may be used as an asset, it doesn’t have an explicit policy ID.

Tokens with the same asset ID are fungible with each other, however they are not fungible with tokens with different asset IDs. An asset ID is a fungible token collection’s unique identifier.

*PolicyID* - The unique ID linked with a minting policy. The ID is a sequence of letters and numbers that is generated by applying a hash function on the policy itself.

Asset name - an asset’s (immutable) property that is used to differentiate amongst assets within the same policy. The asset name, unlike the policyID, does not correspond to any code or set of rules and may be any common term, such as ‘tickets’ or ‘VIPTickets.’ Valid asset names may, however, be limited by the policy that defines how an asset is scoped.

For distinct tokens, various policies might use the same asset names.

**Tokens**

A token is a short word for ‘asset token,’ which is an asset’s on-chain representation and accounting unit. One ada, one home, or a ton of tea, for example, may be represented by a token.

**Currencies**

Currency is a term used to describe a monetary unit that serves as a means of exchange for goods and services. Cardano accepts ada and native tokens, both of which function equally on the network.

However, at this moment, ada is the only currency used to pay fees and make deposits, and it is also the only currency in which rewards are issued. The architecture of the underlying consensus protocol is responsible for this attribute of ada (and no other sort of asset).

Native tokens are a kind of accounting unit that may be used for payments and transactions, as well as being transmitted to an exchange address. Because the Cardano accounting ledger has built-in functionality for tracking ownership and transfer of several types of assets, these tokens are supported by the ledger without the need for extra smart contracts. While both ada and native tokens have value and may be used to pay and transact, only ada is utilized for fees and rewards, and only native tokens can be customized.

**Conditions when using ada**

Cardano’s main currency is ada (₳). Because each address must have a minimum ada value, having ada (along with other currencies) is required to transfer multi-asset tokens between addresses (min-ada-value, currently set at 1 ada).

As a result of its design, the following conditions apply:

- You cannot create outputs only containing custom tokens

- The number of each kind of token in an output can have a slight bearing on the output’s min-ada-value. There is the same effect as the minimum UTXO value takes memory overhead into account when storing it on a computer. The memory overhead isn’t affected greatly by an increase in ada but adding multi-assets does have an impact. This is because the names and policy IDs of each kind of token take up extra space in the output

- When sending custom tokens to an address, the min-ada-value of ada is always sent together with the custom tokens (by including the ada in the same output). The ada supplied with the tokens no longer belongs to the sender, if the address is not spendable by the person sending the tokens. Users may opt to employ off-chain dialogue to discuss who gives the ada to cover the min-ada-value in the output created by the transferring transaction before transferring custom tokens. Typhon wallet is always innovating and they introduced Warp Transactions in 2023, allowing users to send tokens without spending that minimum ADA.[^46]

- To recover the ada stored alongside custom tokens in an output O, the user must either: 

   a) spend the output O and burn the custom tokens therein; or 
   b) spend an output O and an output O’ and consolidate the tokens therein with the same collection of types of custom tokens stored in another output O. (spent within the same transaction) 

For example, in a new output created by the consolidating transaction, (CryptoBisonPolicy, AmericanBison, 2) in O may be consolidated with (CryptoBisonPolicy, AmericanBison, 4) in O’, for a total of (CryptoBisonPolicy, AmericanBison, 6)

- Splitting custom tokens into more outputs than they were before the transaction was executed necessitates using more ada in total to meet the min-ada-value, since ada is required in the extra outputs.

**What are Token bundles?**

A token bundle is a collection of tokens that is heterogeneous (’mixed’). Tokens of any kind may be packaged together. On the Cardano blockchain, token bundles are the standard way to represent and store assets. Token bundles group tokens into a certain data structure, ensuring which tokens are fungible with other tokens is clearly defined.

Ada amounts were stated in transaction and UTXO outputs in prior versions of the Cardano ledger. These amounts have been expanded with token bundles, which may define an ada amount with quantities of other assets in a single output, thanks to the addition of multi-asset functionality.

Token bundles are stored in transaction outputs and mint fields, as well as the UTXO set outputs, which are monitored by the ledger. Certain elements of a transaction, such as the fee field, must still explicitly state ada amounts.

**Token bundle storage**

Token bundles can be found:

- As a transaction’s mint field, indicating that the transaction is producing the bundle’s tokens
- In a transaction’s output or an output in the current UTXO recorded by the ledger, alongside the address of the output, e.g. Multi { MyAddress, value: TB_Example }

**Splitting and combining token bundles**

Token bundles may be split and combined arbitrarily by transactions. 

**Minting policy**

A minting policy is a collection of rules that control the minting and burning of assets that are within the policy’s control. A minting policy specifies the circumstances under which tokens are minted (or burned). The rules might, for example, describe who has authority over the asset supply through minting and burning.

Users that wish to produce a new asset establish the minting policies. For example, a user may choose to limit themself to just minting a certain kind of token. This is something that would be outlined in the policy.

The following are the rules for minting:

As a very simple set of rules, it consists of the following (ANDs and ORs):

- A list of the signatures required to enable the mint to operate (e.g., a multisig specification, where no code is needed)
- With a Plutus Core script, a specification of when the script may be spent (e.g., after slot 10 and before slot 30).

When a transaction is executed, the node checks for compliance with minting regulations by executing the code or validating the appropriate signatures. All minting policies for all assets that the transaction is seeking to mint must be followed.

**Minting: Terms & Conditions**

- A minting policy is required for all assets. Ada’s minting policy, for example, states that ‘new ada can never be minted’
- A token has just one minting policy connected with it
- A single policy describes the requirements for both minting and burning tokens that fall within its ambit. Its compliance is monitored both during minting and during burning
- An asset’s related minting policy cannot be changed at any time, it’s irreversible. Current tokens cannot be linked to a new policy. With a new minting policy, users may purchase back and burn all current tokens while still minting new ones. This is by design, it’s not a fault in the system.
- An existent asset on the ledger that is scoped under a certain policy is guaranteed to have been minted in accordance with that policy
- The actual policy is unimportant until tokens of that policy are generated in a transaction. Its only purpose is to serve as a unique ID for the asset
- Assets related with various minting policies are never interchangeable. They can be exchanged in the same manner as USD can be used to acquire Euros: the quantity of Euros you can buy with a specific amount of USD is determined by the exchange rate. 

**Relationship between an asset and its minting policy**

For security reasons, the link between an asset and its minting policy is permanent. This feature protects users and the system against falsely minted tokens.

When a token’s minting policy changes, it’s no longer the same token, and its value can’t be compared to the original token’s. In order to define high-assurance policies, this permanent asset-policy association method is essential. Cardano’s MA (Multi Asset) technique becomes vulnerable to a variety of attacks if this identification is loosened. It’s best to ensure that every token was minted in line with its minting policy, not any other policy it may have previously been linked with, by having a permanent link between them.

**Minting policy Types**

There are several more sorts of minting policies to consider.

**Single-issuer policy**

A single-issuer minting policy states that only the entity with a certain set of keys may mint tokens for a specific asset group. For example, the minting transaction must have been signed by the set of keys provided in the minting policy.
Tokens representing Panini football cards are an example of an asset category that would adopt a single-issuer policy. The firm that makes authentic collectors’ cards would provide the keys needed to mint fresh football cards, as required by the minting script. This means that no new football card tokens may be produced without the approval of the firm. There is no need to use Plutus smart contracts when creating this form of policy. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/panini.png "Panini soccer cards")         
**Figure 5.3**:  Panini soccer cards

Tokens resembling an artist’s paintings are another example of a single-issuer policy use case. This would rule out the production of new painting tokens without the artist’s signature. The insurance, on the other hand, establishes that all of the existing paintings covered by the policy were properly produced by the artist and nobody else. It enables artists a new medium to express themselves, not to mention a more efficient and fairway to sell and distribute art, as painter Jonathan Dickson[^47] explained in this video.[^48]  

**Time-locked minting policy** 

AKA token-locking. This policy may be used to limit the number of tokens that can be spent from a certain address. 

- only during or after a defined time slot
- only before a defined time slot

Typically, this form of policy isn’t employed on its own. It is often used in combination with a multisignature or single issuer policy, for example. Only a transaction signed by key ‘k’ may spend this output after slot ‘s’. This form of policy may be created without the need for Plutus smart contracts. 

**One-time minting policy**

In a one-time mint policy, a single transaction mints the whole set of tokens for a specified asset category. This indicates that there will never be any more tokens in that asset category. This sort of policy necessitates the use of Plutus smart contracts.

For example, a one-time mint policy may be used to create ticket tokens for the Super Bowl. Because the venue’s capacity is known ahead of time, there will be no need to issue more tickets.

**Minting transactions**

Each transaction has a mint field that may be used to add fresh amounts of new tokens to the ledger (minting) or to remove existent tokens (burning). Minting transactions are transactions in which the mint field is not empty. The usage of this field must be strictly regulated to guarantee that tokens are minted and burned in accordance with the token’s minting policy.

Minting transactions must include the minting rules for the tokens they are minting, in addition to the mint field, so that these tokens may be inspected during validation.

The ledger will record the assets contained in the mint field, which is included in the transaction’s balancing: if the field is positive, then the transaction’s outputs must have more assets than the inputs supply; if it is negative, then they must contain fewer.

It’s worth noting that a single transaction might result in the creation of tokens with numerous minting rules. For instance, (Policy1, SomeTokens) or (Policy2, SomeOtherTokens). A transaction might also mint and burn tokens at the same time.

**Metadata standards**   

So as you may gather, most of the functionality for Cardano native assets is described in its metadata, and the two primary metadata standards allow for a broad range of use cases. The initial standard was CIP-25,[^49] which predated smart contracts on Cardano. These NFTs are easiest to mint, but functionality is limited since smart contracts cannot access the information. 

CIP-68[^50] is a more recent standard and more dynamic in that it enables more sophisticated capabilities with smart contract-readable information. Since smart contracts were introduced on Cardano, this has been the accepted standard. 

Instead of storing metadata as transaction metadata as CIP-25 does, CIP-68 stores it as an inline datum on a UTXO, in the current ledger state. CIP-68 dictates that each token name must be prefixed by a label in brackets, which indicates the purpose of the token. (100) : reference token, (222) : NFT, (333) : FT and (444) : RFT. Rich Fungible Token (RFT) extends what a fungible token is, RFTs can feature images, audio and video. A major advancement with CIP-68 was that NFTs were now updatable, opening up a new world of use cases. 

CIP-60[^51] was proposed by the music streaming marketplace newm.io, extending metadata standards to cater for music tokens. As dApps on Cardano push the boundaries of creativity and innovation, the protocol will need to adapt to facilitate them. Change is managed by the CIP (Cardano Improvement Proposal) process. We’ll discuss this more when we dive into ‘Governance’ in chapter 9. 

Also of note to artists and builders is the NFT Guild[^52] which is in place with a mission to *‘facilitate the creation of a lively NFT developer and creator community and to ensure that projects have the resources they need and a clear understanding of best practices when getting started and throughout their journey in this space.’*

The Cardano Token Registry[^53] allows projects to register off-chain token metadata mapping it to on-chain identifiers (usually hashes of asset IDs, output locking scripts, or token forging policies). The metadata standard described in CIP-26[^54] helps to translate opaque on-chain identifiers to a human readable format. 

## Creating native tokens on Cardano 

Users can select between simple and sophisticated tools to bring their assets to life on Cardano. Many tokenization options[^55] are available in Cardano. The ledger’s accounting architecture handles not just ada transactions, but also transactions that hold several asset types at the same time.

**Utility**

To fulfill commercial or business goals, developers, enterprises, and apps may build general purpose (fungible) or specialized (non-fungible) tokens. Custom payment tokens or rewards for dApps, stablecoins tied to other currencies, and unique assets, like eBooks, that represent intellectual property are just a few examples. All of these assets may then be traded, swapped, or used to purchase goods and services.

Users will be able to transmit, receive, and burn their tokens without paying transaction fees or installing event-handling logic to monitor transactions since native tokens do not need smart contracts to transfer their value. Users are able to produce, distribute, trade, and store tokens in one of four ways, depending on their preferences and technical expertise:

**1. Cardano CLI**

Developers may create (mint) assets and submit test transactions to various addresses using the native tokens testing environment.

Because of the nature of working with the CLI, it is assumed that you are comfortable with setting up and administering a Cardano node, as well as dealing with transactions and managing addresses and values. To generate native tokens using Cardano CLI, follow the steps outlined in the documentation.[^56] At a high level, the steps are as follows:

- Create and start a Cardano node 
- Generate verification and signing keys
- Generate a payment address, fund and check the balance 
- Start the minting process, create a policy and mint a new asset
- Lastly, build the raw transactions, submit and sign transactions to send the tokens to the target address. 

The Cardano Developer Portal[^57] provides native token tutorials and exercises to enable developers create tokens, implement monetary rules, and understand how to conduct multi-asset transactions.

**2.  GUI-based solutions** 

NMKR (pronounced N-Maker) enables users to manage NFT projects through simple ‘point and click’ experience. 

It is a favourite for less technical users wishing to generate tokens. The graphical user interface that simplifies the process of creating tokens. To make a token, just fill in the following fields:

- The token’s name (for example, CardanoForTheMasses)
- the token’s symbol (for example, CFTM)
- the token’s logo (upload)
- Amount to be made (eg, 10m)
- Cardano payout wallet address

It's best to watch a tutorial on YouTube to see how easy it really is, or follow along NMKR’s friendly documentation.[^58]

**3. Third party platforms**

adaHandle ($handle, adahandle.com) was one of the first projects to launch after Goguen as *‘An NFT-powered naming solution for your Cardano wallet address, secured entirely on-chain via the Handle Standard’*. It is a little like having your own internet domain, eg. $cardanobook is twinned with cardanobook.com

Another early project was Dripdropz (dripdropz.io), the ‘Cardano Token Distribution System’ has added great value to the ecosystem.

There are new projects launching every week, visit sites like *CardanoCube.io* to browse for what you want.

## The lifecycle of native tokens on Cardano

The native token lifecycle will be complete after all of the required components have been deployed. It is divided into five stages: 

- Minting
- Issuing
- Using
- Redeeming
- Burning

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/lifecycle.png "Native tokens lifecycle")
**Figure 5.4:**  Lifecycle of native tokens on Cardano

Each of these logical processes includes Cardano blockchain transactions, which may result in ada fees. The following are the primary actors:

- Asset controllers, who determine the asset class’s policy and authorize token issuers to mint and burn tokens. They might also retain co-signing rights for any tokens that are minted or burned
- Token issuers, who create new tokens, keep a reserve of them in circulation, distribute them to token holders, and destroy them when they’re no longer useful
- Token holders, who keep tokens, send them to other users, use them for payment, and then redeem them with the issuers when they’re no longer needed. Normal ‘Joe Soap’ users, exchanges, and other entities may be token users.

The lifespan of multi-asset tokens begins with their creation – minting, which is the process by which one or more token issuers generate new tokens in line with the monetary policy script provided by the asset controller. In most cases, new tokens will be issued to serve a particular function. Tokens that are fungible or non-fungible (unique) may be developed for particular payment, buying, or exchange requirements, for example. When a new token is created, the overall token supply for that token grows, but the ada supply remains the same. Minting coins and transferring them to new addresses may need the payment of ada, which might be proportional to the quantity of distinct tokens possessed.

Token holders will store tokens in their wallets and will be able to transfer them on to other users, swap them for objects of value (including non-native tokens), and so on, just like they would with ada. When a user’s token has been used up, they may opt to redeem it. Meaning tokens are returned to their original issuer (perhaps in return for a product, service, or some other currency, for instance). Tokens may then be re-issued to other users as required after they were redeemed. To pay for transaction fees, token holders will need to keep some ada in their wallets.

If required, tokens may be burnt when they become redundant, in line with the underlying monetary policy script. The act of burning these tokens eliminates them (removing them from circulation), reducing the overall token supply. At this time, any deposits will be refunded. Fungible and non-fungible tokens are both burned in the same way.

The multi-asset token lifecycle may enable tokens to be acquired and reissued by other parties, such as token holders acting as reissuers. This may be done to facilitate trading across different asset classes, maintain liquidity in one or more tokens (by serving as a broker), or reduce the effort/cost of token minting, issuance, or metadata server maintenance, for example. As a result, such a transaction benefits both reissuers and issuers by reducing costs and effort, preserving separation and integrity, and infusing value into the asset class.

## Min-ada-value requirement

On the ledger, UTXOs may contain a mixed bag of tokens, including ada. The maximum total size taken up by UTXO entries on the ledger at any one moment is limited by requiring some amount of ada to be included in every UTXO (where that amount is dependent on the size of the UTXO, in bytes).

By adjusting the min-ada-value setting, the maximum permissible UTXO size (the total of the sizes of all UTXO entries) is implicitly modified. The limitation prevents the Cardano ledger from going above a specific size in this manner. A ledger without size restrictions is prone to becoming overburdened with data to the point that users will be unable to process it (or operate a node) on devices that satisfy the required node criteria.   

There is more detail in the documentation[^59] on the ‘ada-only’ case, ‘min-ada-value’ calculation and with worked examples.

**Native Assets in the wild** 

So far we’ve talked mostly about the theory of native assets on Cardano. To get a better feel for how powerful the native asset standard is when paired with eUTXO, visit the graphical explorer, eUTxO.org, particularly the stats page which lists some of the notable transactions to date. 


![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/eutxoorg.png "eutxo.org")
Figure 5.5:  eutxo.org/stats/records

## Smart Contracts Rollout

Alonzo built on Cardano’s token improvements to provide developers with the tools they needed to create dApps. IOG laid the groundwork for Cardano to become a smart contract platform by introducing transaction metadata,[^60] token-locking[^61] with *Allegra* in December 2020, and native token issuance.[^62]  Shortly after came *Mary*, a multi-asset protocol update in March 2021 that enabled users to create native tokens for Cardano transactions.

These features were built into *Alonzo*, the following protocol update in September 2021. Alonzo contributed functionality for smart contracts (digital agreements) to Cardano leveraging the novel hard fork combinator. By facilitating the construction of smart contracts and decentralized apps (dApps) for decentralized finance (DeFi), it offered up new possibilities for developers.

**Plutus Scripting**

IOG developed the essential tools and infrastructure with *Alonzo* to enable Plutus Platform application development. *Alonzo* enhanced Cardano Shelley’s basic multi-signature scripting language (multisig) with a rigorous methodology based on formal methods and verification. For more sophisticated and secure scripting capabilities, Multisig was updated to the Plutus Core language. The Alonzo ledger uses Plutus Core to enable advanced scripting leveraging the extended unspent transaction output (eUTXO) accounting model.

The foundation for smart contracts must be both safe and dependable. As a result, Haskell was selected as the programming language for Plutus Core smart contracts. Haskell is a high-level programming language that is used by developers to code, which is then compiled into Plutus Core.[^63]

Haskell has been around since 1987, and it stands out among programming languages because of its high degree of trustworthiness. Smart contracts written in Haskell, using the Plutus framework, are designed to accomplish precisely what is expected of them and can be checked for correctness before being implemented. This ensures that smart contracts written on Cardano will be simple and secure, which is critical for applications that manage automated trading or large-scale money transfers.

**What smart contracts technology is currently available?**  

Of the 18,000 cryptocurrencies[^64] around today, with only approximately 80 having smart contracts according to CryptoSlate.[^65] PolkaDot, Solana and Ethereum are among the participants on the market that support smart contracts. Technology is changing to suit the market needs for systems that are quick, secure, accurate, and dependable. Many firms have attempted to install large-scale apps on these platforms and have run across ‘issues’. For example, the DAO hack,[^66] the Parity bug and the shambolic Solana Wormhole hack[^67] where $320m went missing. Despite recurring hacks and rug pulls,[^68] the most critical problems in smart contracts continue to surface.[^69] Anyone can write buggy, insecure code however Cardano strives for higher standards with a functional programming model supported with rigorous property-based testing and regular audits.

## UTXO alliance

IOG collaborates with other UTXO-based blockchains to develop novel solutions that will improve interoperability, programmability, and scalability. IOG announced a partnership with Ergo (ergoplatform.org), Nervos (nervos.org), and Topl (topl.co) to form the UTXO alliance during the 2021 Cardano Summit.[^70] They then invited Komodo (komodoplatform.com), Alephium (alephium.org) and DigiByte (digibyte.org) into the alliance as well.

The UTXO alliance will help cross-ecosystem activities to expand UTXO’s smart contract capability. The joint goal of collaborating with other blockchain sector initiatives is to stimulate and support further research, development, and education throughout the whole area.

The UTXO alliance’s purpose is to keep the UTXO model evolving in terms of interoperability, scalability (sharding,[^71] state channels, etc), and smart contract solutions. Improving these solutions and leading major projects to develop bridges across blockchains enables everyone to have access to fair and accessible global finance. This also provides a collaborative effort to promote UTXO-based ledgers in the industry. Bitcoin is obviously the most well-known UTXO blockchain but spin-offs like Bitcoin Cash, Litecoin, and Zcash are among the other projects that use this approach.

**Building bridges**

Instead of depending on expensive middlemen, blockchain technology tackles the difficulties of centralization by allowing trustworthy peer-to-peer transactions based on cryptographic verification. To create a safe and decentralized environment for financial transactions, several blockchain solutions have developed. While these initiatives differ in terms of consensus protocols, accounting models, and smart contract approaches, they all concentrate on similar use cases.

DeFi Growth[^72] has been consistent and shows no signs of slowing. However, fragmented ecosystems, differing governance standards, technology versions, and feature support slow the development of the blockchain environment. Nasdaq’s forecast on DeFi Growth is shared by Romain Pellerin, IOG technology chief: 

> Mainstream blockchain adoption will pass only through the interconnection of networks, similar to how the Internet was built by the interconnection of intranets and extranets.

With this in mind, it’s critical to guarantee that the whole sector is working toward interoperability. Users should be able to interact with one another without being bound by a single ledger, smart contracts should work in a variety of contexts, and decentralized apps (dApps) should be cross-platform compatible. Only in this manner will the blockchain sector be able to realize its full potential, resulting in increased adoption.

**No one-size-fits-all**

The UTXO alliance is also interested in blockchain programmability enabling the development of dApps and smart contracts. In reality, new languages must be created to adapt to the UTXO model’s particular transaction and data storage management (for example, Ergo’s[^73] and Cardano’s eUTXO). Antara, CKB-VM, ErgoScript, and Plutus are the smart contract languages created by the alliance’s founding members. To quickly extend the number of use cases that may be executed on UTXO-based blockchains, alliance members are pooling expertise and cooperating in the development of such technologies.

Furthermore, such languages are constructed as domain-specific languages (DSLs) on top of widely used programming languages such as Scala, Haskell, C, JavaScript, Go, Rust, and others. Those mainstream languages, however, may not always provide the security or convenience of use that smart contract developers seek.

IOG selected Haskell as the programming language for Plutus smart contracts to guarantee increased security and code verifiability. For application development, it is the most extensively used functional programming language. Haskell is a secure and formally verified programming language. In terms of acceptance, it is appropriate for a broad variety of financial use cases, providing for quick transfers of payments, accurate outcomes, and scalability. In terms of state distribution and parallelization for increased scalability, this programming approach works well inside the UTXO model.

The UTXO alliance will investigate the best-case scenarios for creating a uniform smart contract landscape where a range of programming languages may be built and utilized on various blockchain platforms, taking into account various development initiatives. This will be critical in enabling more blockchain interoperability.

**True Scalability**

It’s also vital to consider a network’s scalability potential in terms of transaction processing and throughput as it expands. Because the UTXO model is based on the local state, it differs from the account-based model and hence necessitates a distinct programming paradigm.

These two models have diverse features and provide different trade-offs, different benefits and drawbacks. The account model promotes the creation of use cases that depend on the global state, but the UTXO model assures determinism, predictability, and scalability by managing local states, meaning small sections of the overall graph of transactions. This slows things down as the whole graph of transactions needs to be processed before validation.

As a result, the UTXO architecture has the advantage of ensuring the execution of transactions and contracts prior to their submission to the blockchain, with no fees or validation surprises. Also, since it is easier to shard a graph of transactions by breaking it into a collection of sub-graphs, the UTXO paradigm will enable higher scalability.

It’s also simpler to detach a specific transaction or collection of transactions (that transfer data, scripts, and assets) and continue work off-chain before returning to the mainchain with a result, ensuring scalability by off-loading operations off the mainchain. IOG, for example, has created Hydra state channel solutions that boost system performance while allowing several tasks to occur in parallel without sacrificing scalability. To learn more, read about concurrency[^74] on Cardano. Hydra[^75] and other scalability solutions are covered in Chapter 8.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/alliance.png "EUTXO alliance")
**Figure 5.6:** Slide from James Aman’s talk ‘UTXO Alliance’ at ScotFest

[^01]: **Digital footprint** or digital shadow refers to one’s unique set of traceable digital activities, actions, contributions and communications manifested on the Internet or on digital devices. On the World Wide Web, the internet footprint; also known as cyber shadow, electronic footprint, or digital shadow, is the information left behind as a result of a user’s web-browsing and stored as cookies.
[^02]: A **directed acyclic graph** is a directed graph with no directed cycles. That is, it consists of vertices and edges, with each edge directed from one vertex to another, such that following those directions will never form a closed loop.
[^03]: **Transaction output**: Outputs produced by transactions. They are consumed when they are spent by another transaction. Typically, some kind of evidence is required to be able to spend a UTXO, such as a signature from a public key, or (in the Extended UTXO Model) satisfying a script.
[^04]: The **address** of a UTXO says where the output is ‘going’. The address stipulates the conditions for unlocking the output. This can be a public key hash, or (in the Extended UTXO model) a script hash.
[^05]: A **script output**: A UTXO locked by a script.
[^06]: **Redeemer**: The argument to the validator script which is provided by the transaction which spends a script output.
[^07]: A **validator script** is the script attached to a script output in the Extended UTXO model. Must be run and return positively in order for the output to be spent. It determines the address of the output.
[^08]: **Validation context**: A data structure containing a summary of the transaction being validated, and the current input whose validator is being run.
[^09]: The term **Parallelism** refers to techniques to make programs faster by performing several computations at the same time.
[^10]: Fernando Sanchez, ‘Cardano’s extended UTXO accounting model’, iohk.io/en/blog/posts/2021/03/12/cardanos-extended-utxo-accounting-model-part-2/
[^11]: Jean-Frédéric Etienne, ‘Architecting dApps on the EUTXO ledger’, iohk.io/en/blog/posts/2021/11/16/architecting-dapps-on-the-eutxo-ledger/
[^12]: SundaeSwap blog, sundaeswap-finance.medium.com/sundaeswap-labs-presents-the-scooper-model-678d6054318d
[^13]: What is ERGO + ERGOdex Concurrency Solution For Cardano, youtube.com/watch?v=xlDlNmIFrFM
[^14]: Cardano with Paul, youtube.com/watch?v=xlDlNmIFrFM
[^15]: IOHK Lobster challenge, github.com/input-output-hk/lobster-challenge/tree/concurrency-multisig
[^16]: Order book pattern, plutus-apps.readthedocs.io/en/latest/plutus/explanations/order-book-pattern.html#what-is-the-order-book-pattern
[^17]: EUTXO handbook, ucarecdn.com/3da33f2f-73ac-4c9b-844b-f215dcce0628/EUTXOhandbook_for_EC.pdf
[^18]: Neither Smart Nor Contracts: Smart Contracts Need a Rebrand, netguru.com/blog/smart-contracts
[^19]: Surprise AMA 03/31/2019, youtu.be/sc4D2KrvaNA?t=2315
[^20]: Blockchain Certificates (Academic & Others), unic.ac.cy/iff/blockchain-certificates/
[^21]: In economics, **fungibility** is the property of a good or a commodity whose individual units are essentially interchangeable, and each of its parts is indistinguishable from another part.
[^22]: Atala PRISM, atalaprism.io/
[^23]: Ledger sync, github.com/cardano-foundation/cf-ledger-sync
[^24]: CF identity wallet, identity.cardanofoundation.org/
[^25]: Cardano Foundation Partners with Georgian National Wine Agency, cardanofoundation.org/en/news/cardano-foundation-partners-with-georgian-national-wine-agency/
[^26]: Technical collaboration with Epoch Sports & Merchandise, cardanofoundation.org/en/news/technical-collaboration-with-epoch-sports-merchadise/
[^27]: Cardano Store, store.cardano.org/pages/authenticated-products
[^28]: A hash tree or **Merkle tree** is a tree in which every leaf node is labeled with the hash of a data block, and every non-leaf node is labeled with the cryptographic hash of the labels of its child nodes. Hash trees allow efficient and secure verification of the contents of large data structures. Hash trees are a generalization of hash lists and hash chains.
[^29]: **CBOR (Concise Binary Object Representation)** is a binary data serialization format loosely based on JSON. Like JSON it allows the transmission of data objects that contain name–value pairs, but in a more concise manner. This increases processing and transfer speeds at the cost of human-readability.
[^30]: **Concise data definition language (CDDL)** expresses Concise Binary Object Representation (CBOR) data structures. Its main goal is to provide an easy and unambiguous way to express structures for protocol messages and data formats that use CBOR or JSON (JavaScript Object Notation).
[^31]: Transaction Metadata, github.com/input-output-hk/cardano-node/blob/master/doc/reference/tx-metadata.md
[^32]: Alan McSherry, ‘Getting to grips with metadata on Cardano’, iohk.io/en/blog/posts/2020/11/03/getting-to-grips-with-metadata-on-cardano/
[^33]: **Ethereum ERC20 Contract** is a standard for building tokens on the Ethereum Blockchain. Before ERC20 tokens, Cryptocurrency exchanges had to build custom bridges between platforms to support the exchange of any token. For this reason, six rules were created by an Ethereum developer named Fabian Vogelsteller and placed under the name ERC20, which means ‘ethereum request for comment.’
[^34]: **ERC721** is a free, open standard that describes how to build non-fungible or unique tokens on the Ethereum Blockchain.
[^35]: **Token**: A cryptographic token that reflects the value as defined by the community, market state, or self-governed entity. A fungible or non-fungible token may be used as a payment unit, a reward, a trade asset, or a data holder.
[^36]: What’s all the fuss about NBA top shot?, si.com/nba/2021/03/17/nba-top-shot-crypto-daily-cover
[^37]: **Gas (Ethereum)** refers to the fee, or pricing value, required to successfully conduct a transaction or execute a smart contract on the Ethereum blockchain platform. Priced in small fractions of the cryptocurrency ether, commonly referred to as gwei or sometimes nanoeth, the gas is used to allocate resources of the Ethereum Virtual Machine (EVM) so that decentralized applications such as smart contracts can self-execute is a secured fashion. The maximum amount of gas that you’re willing to spend on a particular transaction is known as the gas limit.
[^38]: ‘$300m in cryptocurrency’ accidentally lost forever due to bug, theguardian.com/technology/2017/nov/08/cryptocurrency-300m-dollars-stolen-bug-ether
[^39]: 3 Reasons Solana Isn’t Really Decentralized, makeuseof.com/reasons-solana-isnt-really-decentralized/
[^40]: **Utility token**: a digital token that represents a certain project or environment and has specific capabilities. These tokens may be used as payment units, prizes, or as a means of gaining entry to a particular network.
[^41]: Blockchain Vulnerabilities: Vulnerable ERC20 Tokens and How to Avoid Writing Vulnerable Code, apriorit.com/dev-blog/555-erc20-token-vulnerability
[^42]: What is a native token and how does it compare to ada and ERC20?, github.com/input-output-hk/cardano-ledger-specs/blob/master/doc/explanations/features.rst
[^43]: Welcome to native tokens on Cardano!, youtube.com/watch?v=PVqsCXh-V5Y
[^44]: Blockchain Insights, datastudio.google.com/u/0/reporting/3136c55b-635e-4f46-8e4b-b8ab54f2d460/page/p_wxcw6g0irc
[^45]: Statistics to date (updated weekly), essentialcardano.io/development-update
[^46]: Typhon wallet warp transactions, medium.com/@StricaHQ/introducing-warp-transactions-689d3e1339c7
[^47]: Twitter Jonathan Dickson, twitter.com/JonathanDickson
[^48]: Jonathan Dickson Elements NFTs on Cardano, youtube.com/watch?v=F1DR-39RN28
[^49]: CIP 25 Media token metadata standard, cips.cardano.org/cip/CIP-0025
[^50]: CIP 68 Datum metadata standard, cips.cardano.org/cip/CIP-0068
[^51]: CIP 60 Music token metadata, cips.cardano.org/cip/CIP-0060
[^52]: NFT Guild, nft-guild.io/
[^53]: Cardano Token Registry, github.com/cardano-foundation/cardano-token-registry
[^54]: Cardano off-chain metadata, cips.cardano.org/cip/CIP-0026
[^55]: Tim Harrison, ‘Native Tokens on Cardano’, iohk.io/en/blog/posts/2020/12/08/native-tokens-on-cardano/
[^56]: Getting started with native tokens, docs.cardano.org/native-tokens/getting-started
[^57]: Discover native tokens, developers.cardano.org/docs/native-tokens/
[^58]: NMKR docs, docs.nmkr.io/nmkr-studio/how-to-quick-start-tutorials/how-to-add-tokens
[^59]: Min-ada-value, cardano-ledger.readthedocs.io/en/latest/explanations/min-utxo-mary.html
[^60]: Alan McSherry, ‘Bringing new value and utility to the Cardano blockchain’, iohk.io/en/blog/posts/2020/10/29/bringing-new-value-and-utility-to-the-cardano-blockchain/
[^61]: Kevin Hammond, ‘Goguen brings token locking to Cardano’, iohk.io/en/blog/posts/2020/12/02/goguen-brings-token-locking-to-cardano/
[^62]: Tim Harrison, ‘Building native tokens on Cardano for pleasure and profit’, iohk.io/en/blog/posts/2021/02/18/building-native-tokens-on-cardano-for-pleasure-and-profit/
[^63]: Michael Peyton Jones, ‘Plutus Tx: compiling Haskell into Plutus Core’, iohk.io/en/blog/posts/2021/02/02/plutus-tx-compiling-haskell-into-plutus-core/
[^64]: Adam Hayes, ‘10 Important Cryptocurrencies Other Than Bitcoin’, investopedia.com/tech/most-important-cryptocurrencies-other-than-bitcoin/
[^65]: CryptoSlate Smart Contract Coins, cryptoslate.com/cryptos/smart-contracts/
[^66]: The DAO Hack Explained: Unfortunate Take-off of Smart Contracts, ogucluturk.medium.com/the-dao-hack-explained-unfortunate-take-off-of-smart-contracts-2bd8c8db3562
[^67]: More than $320 million stolen in latest apparent crypto hack, cnbc.com/2022/02/02/320-million-stolen-from-wormhole-bridge-linking-solana-and-ethereum.html
[^68]: A rug pull is a crypto scam in which fraudsters lie to the public to attract funding and quickly run off with investors' funds and/or digital tokens.
[^69]: Nikolic, Kolluri, Sergey, Saxena, Hobor (2018), Finding The Greedy, Prodigal, and Suicidal Contracts at Scale, arxiv.org/pdf/1802.06038.pdf
[^70]: UTXO alliance announcement, summit.cardano.org/sessions/taking-outputs-as-inputs
[^71]: **Sharding** splits a blockchain company’s entire network into smaller partitions, known as ‘shards.’ Each shard consists of its own data, making it distinctive and independent when compared to other shards.
[^72]: Why Privacy and Interoperability Will Fuel Exponential Growth in DeFi, nasdaq.com/articles/why-privacy-and-interoperability-will-fuel-exponential-growth-in-defi-2021-03-04
[^73]: Learning Ergo 101 : eUTXO explained for human beings, dav009.medium.com/learning-ergo-101-blockchain-paradigm-eutxo-c90b0274cf5e
[^74]: Olga Hryniuk, ‘Concurrency and all that: Cardano smart contracts and the EUTXO model’, iohk.io/en/blog/posts/2021/09/10/concurrency-and-all-that-cardano-smart-contracts-and-the-eutxo-model/
[^75]: Sebastian Nagel, ‘Hydra – Cardano’s solution for ultimate Layer 2 scalability’, iohk.io/en/blog/posts/2021/09/17/hydra-cardano-s-solution-for-ultimate-scalability/
