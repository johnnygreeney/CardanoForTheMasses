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

An unspent transaction output (UTXO) is the term for the amount of digital currency that remains after a transaction. The flow of assets is documented in a UTXO model as a directed acyclic graph with nodes representing transactions and edges representing transaction outputs, with each successive transaction consuming some UTXOs and adding new ones. Users’ wallets determine the users’ balance by keeping track of a list of unspent outputs connected with all addresses held by the user.

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

An address (which you might view as a lock) and a value are included in the transaction output. In line with this analogy, the address’s signature is the key that unlocks the output. An output may be used as an input after it has been unlocked. New transactions use previous transactions’ outputs while also producing new outputs that may be consumed by subsequent transactions. Each UTXO may only be used once, and it must be consumed in its entirety. Only one input may spend each output.

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

Furthermore, eUTXO expands on the UTXO concept by enabling output addresses to include complicated logic to determine which transactions are allowed to unlock them, as well as by allowing custom data to be added to all outputs. When verifying an address, the script will look at the data carried by the output, the transaction being checked, and some extra data known as redeemers that the transaction supplies for each input. The script provides enough context to deliver a ‘yes’ or ‘no’ response, in what may be very complicated circumstances, by uncovering all of this information.

eUTXO allows for arbitrary logic to be expressed in the form of scripts. This arbitrary logic examines the transaction and data to determine whether or not the transaction may use an input.

The graph structure of the UTXO paradigm differs significantly from the account-based model employed by several current smart-contract enabled blockchains. As a consequence, design paradigms for dApps on account-based blockchains do not easily adapt to Cardano. Because the underlying representation of the data is different, new design patterns are required.

The per-branches architecture of the UTXO (Bitcoin) model is carried over to eUTXO, where one branch is defined as a series of transactions requiring a succession of validations. Building dApps and other solutions with numerous UTXOs is vital for splitting the functionality over various branches and enforcing additional parallelism. This has benefits when trying solve the scalability conundrum. More about Scalability in Chapter 8 (Basho).

**eUTXO Advantages**

Compared to other accounting models, the eUTXO model has several distinct benefits. The transaction’s success or failure is solely determined by the transaction and its inputs, not by anything else on the blockchain. As a result, before a transaction is posted to the blockchain, the legitimacy of the transaction may be confirmed off-chain. A transaction may still fail if another transaction consumes an input that the transaction is expecting at the same time, but if all inputs are still available, the transaction will succeed.

This contrasts with an account-based approach (such as Ethereum), which allows a transaction to fail in the middle of its execution. In eUTXO, this will never happen. Also, transaction execution costs may be calculated off-chain before transmission, which is something that Ethereum does not allow.

Cardano’s eUTXO paradigm provides a safe and flexible environment for processing many operations without causing system issues. This architecture provides superior scalability and privacy, as well as more straightforward transaction logic, since each UTXO can only be used once and in its entirety, making transaction verification considerably easier.

The eUTXO model has the advantage of being able to forecast the fees necessary for a successful transaction before it is posted. This is a feature that account-based models do not have. Account-based blockchains, such as Ethereum, are indeterministic, meaning the impact of a transaction on the chain cannot be guaranteed. This ambiguity raises the danger of financial loss, unexpectedly expensive costs, and a broader attack vector for hackers to exploit. 

A deep technical analysis of eUTXO ledger’s architecture is beyond the scope of this book, however, you can get ‘into the weeds’ by reviewing IOG’s blog ‘Architecting dApps on the eUTXO Ledger’ where they provide a sample architecture. SundaeSwap and Axo (previously Maladex) also blogged about their solution while *Spectrum Finance* (formerly known as ERGOdex) talked about their philosophy on *Cardano with Paul* YouTube channel. There are also some code samples from IOG on avoiding concurrency using multi signatures in the Lobster Challenge. IOG analyze a sample order book pattern architecture in their blog. For a deeper dive into eUTXO, read the handbook.

## ’Neither smart nor a contract’

While Vitalik Buterin and others have opined that smart contracts are neither smart nor a contract, let’s not be pedantic for the sake of brevity. A smart contract is a code-based automatic digital agreement that records, validates, and executes the contract’s binding transactions between numerous participants. When preset criteria are satisfied, the smart contract code automatically executes the contract’s transactions. A smart contract is just a brief program whose inputs and outputs are blockchain transactions.

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

**March 31, 2019. On metadata.** CH:

> An example of this…. let’s say that Bob goes to an ATM and withdraws $300 of value out of an ATM …now that’s a transaction …now let’s say Bob did that next in an Italian restaurant on his birthday and all of his friends happen to be there …you would say ‘oh it looks like Bob’s pulling money out to pay the check’ ….or in some way is connected to this event, he’s at a celebration, there’s people there…. it’s expensive and let’s say it’s at 12 o’clock …it’s lunchtime… Bob can then go take 300 dollars from an ATM, so the same type of transaction but now I’ve changed the metadata…
> 
>Let’s say it's 2:00 a.m. right next to a known brothel ….so basically the exact same type of transaction …the same type of value, the same actor involved… this is his account and his money, but because you’ve changed the metadata it has vastly different implications…. So, what if you could swap these metadata and then suddenly you can now make the Italian restaurant look like a brothel? …whoever controls that story has a lot of power.

With the advent of Bitcoin, developers began using blockchain technology to add small amounts of new data to the chain, knowing that the data would be accessible for the rest of time. In 2015, the University of Nicosia became the first university to issue academic certificates whose authenticity could be verified through the Bitcoin blockchain. Adding information to the chain became the norm over time. 

**Transaction metadata**

Metadata is a useful tool for certifying and validating information. It lets cryptocurrency assets save information about their previous owners, transfers, and values. This is especially useful when dealing with non-fungible assets that reflect value, such as property or intellectual property. A public key may also be used to sign and certify a variety of documents, proving the document’s authenticity.

One of the most well-known applications of metadata is in the supply chain. Factories, customers, suppliers, and delivery services are all part of the supply chain. Participants must give proof of interconnected services that are available to everyone for verification in order to allow effective data tracking. In this situation, metadata may give a full view of supply chain activities by combining fixed data on the blockchain ledger with metadata. For all parties, this ensures openness, immutability, and confidence.

**Atala**

IOG’s Atala product suite, which includes Atala PRISM, Atala Trace, and Atala Scan solutions, saw early commercialization of metadata deployment on Cardano. The IOG team is developing metadata support while connecting with the Cardano ledger to improve the entire product functionality in terms of data feasibility, accountability, and traceability.

Atala PRISM is a decentralized identification system that allows individuals to control their personal data and communicate with organizations in a seamless, private, and safe manner. On Cardano, the Atala PRISM team is using metadata to certify and store DIDs and DID documents. It will also be able to cancel credentials such as university certificates, in addition to creating them.

Atala Trace and Atala Scan are being developed to help brand owners get a better understanding of supply chain operations while also establishing product provenance and auditability. Metadata integration will be employed in these circumstances to store tamper-proof supply-chain information.

Transaction metadata was an early component of Goguen utility and smart contract capability, which were expanded and developed by a variety of additional features.

**Cardano Foundation partnerships** 

In line with their open source strategy, the Cardano Foundation leveraged Ledger Sync and the Identity Wallet to deliver the Bolnisi track and trace solution. The Bolnisi winemakers have already tracked 100,000 bottles of wine on Cardano. This project sets a precedent for future work, leveraging Web3 technology to verify a product's proof of origin and authenticity. This solution is reproducible for similar challenges with counterfeit goods across many industry verticals. 

I'ts no secret that the fashion industry loses billions each year from counterfeit products. The Cardano Foundation partnered with *Epoch Sports* and *Merchadise* to address the issue of licensed intellectual property. NFC chips linked to on-chain records on the Cardano blockchain verify the authenticity of their jerseys while also enabling more consumer engagement. The same solution is in place for the proof-of-concept (POC) hoodie in the Cardano store. The CF plans to publish all technical details on the Developer Portal in due course.

**Cardano’s metadata strategy**

Metadata has a wide range of applications. With this in mind, IOG has been trying to make it as simple as possible for developers to include metadata into their applications. IOG also want to ensure that ada holders have a simple means to see information about their transactions.

**Differentiators**

Metadata conveys a transaction’s narrative, and there are several methods to engage with it. Ada users may search for particular information in the Cardano Explorer, and developers can make use of metadata by embedding details directly into a transaction. The data may be directly contributed, or a Merkle tree of the data can be created and the root hash of the Merkle tree placed on the blockchain for larger data sets. Once this is completed, it can be shown that the data exists at a certain moment in time and that it is permanently stored on the chain for future use.

It’s also worth noting that transaction information is recorded on the blockchain and sent with every transaction. The fact that it is kept on-chain rather than in the ledger state is advantageous since it has no impact on transaction validation and does not degrade ledger performance.

The additional cost is that metadata increases the transaction’s size in bytes, and the processing speed is dependent on transaction size. The Concise Binary Object Representation (CBOR) and Concise Data Definition Language (CDDL) notations may be used to create metadata. Check the Cardano wallet’s transaction metadata and how to use transaction metadata schemes in Cardano CLI.

## Token Locking on Cardano 

**_Rest of chapter to be uploaded soon..._**



[^01]: **Digital footprint** or digital shadow refers to one’s unique set of traceable digital activities, actions, contributions and communications manifested on the Internet or on digital devices. On the World Wide Web, the internet footprint; also known as cyber shadow, electronic footprint, or digital shadow, is the information left behind as a result of a user’s web-browsing and stored as cookies.
[^02]:
[^03]:
[^04]:
[^05]:
[^06]:
[^07]:
[^08]:
[^09]:
[^10]:
[^11]:

[^70]:
[^71]:
[^72]:
[^73]:
[^74]:
