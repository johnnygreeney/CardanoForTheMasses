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
