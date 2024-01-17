# Chapter 6: Plutus

*‘There is no honest man! not one, that can resist the attraction of gold!’* <br>
― Aristophanes

<br><br>

There are a lot of moving parts in terms of a dApps architecture. We won’t be teaching you ‘how to code’ in the next few chapters, but you should get a good feel for the different languages, tools and services available. The various playgrounds and interactive programming tutorials arguably offer a more intuitive experience when you decide to code your first program. If blockchain is a minefield of jargon, then programming is just another patch you must traverse. Lets quickly run through some of the terms and phrases you will encounter. 

The **expressiveness** of a programming language is how easy it is to represent and communicate your ideas in a language. Kind of like the size of the vocabulary you have at your disposal.

**Imperative programming** is where we provide the computer with step-by-step instructions on HOW to execute a task. **Declarative programming** involves specifying WHAT result we're expecting from our code, without explicitly specifying step-by-step instructions.

**Functional programming** is a form of declarative programming that uses expressions and functions without mutating state and data. Although these restrictions can mean a less expressive syntax, functional programming places a focus on writing clear, understandable code that is less buggy.

A **compiler** translates code from a high-level language (eg. Python or JavaScript) into **machine code** before a program runs it. Whereas an **interpreter** may sound similar, except it translates the code written in a high-level language into machine code line-by-line as the code runs.

While compilers and interpreters convert high-level language into machine language, **assemblers** convert low-level language, or assembly language code, into machine language

**Machine language** is the binary digits, or 0s and 1s, that a particular computer can execute directly. Machine language is translated into **assembly language**, which is in hexadecimal form for human consumption.  

A **toolchain** set of software utilities used in programming, ie. the tools used to translate source code into a machine language code are the compiler, assembler, linker and debugger. 

When you hear somebody say ‘​​X is a first class citizen on Cardano’ …well in programming, being a first-class citizen usually means some entity which supports all the operations available to other entities. There is a subtle distinction from a ‘higher-order function’ which operates on other functions.

**LSP**, or Language Server Protocol is a term you may encounter… just think of it as an open protocol used between code editors. LSPs provide ‘language intelligence tools’ that make a developer’s life easier such as highlighted syntax, friendly error messages, auto-code completion which is kind of like predictive text on your phone. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig61.png "figure 6.1")
**Figure 6.1**  Plaintext v Program, drawing credit @ktorz 

There are different levels of programming languages. On one extreme, there are some very expressive ‘high-level’ languages closer to English. At the other end of the spectrum, there are ‘low-level’ languages closer to actual machine language. It’s all relative, depending where you sit on the spectrum.

For programming code to run on a computer, it first needs to be translated into machine code by a compiler. The computer can digest machine code much easier than a high-level programming language. If a language is very ‘high-level’ it may need to be translated into an intermediate representation (compilation target) before it can be translated further into the lowest level 1s and 0s the computer executes. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig62.png "figure 6.2")
<br>**Figure 6.2**   Compiler drawing by @_KtorZ_ 

Then you will also hear talk of domain-specific languages (DSL). A DSL is a language specific to a particular application domain like finance or law. A general-purpose language can be used across a wide range of domains. 

Following on from this, there are also embedded domain-specific languages (eDSL). These are more succinct programming languages written on top of an existing programming language. Imagine these as pre-built lego blocks coded for you in a specific language that can be used for well-defined tasks. They are usually friendlier for beginners and are also useful for representing smart contracts. Embedded DSLs are popular on Cardano because they can smoothly integrate with off-chain code and often allow reuse of the host language existing tools.

A **virtual machine** (VM) is a digital version of a real life physical computer. You can view it as the same thing in terms of its functionality and capabilities. A VM can execute programs and operating systems, store your data, connect to WiFi and requires security and patching just like a normal computer. The VM software is just a computer file, known as an image, that acts like an actual computer. It can run a different (OS) operating system and this is where VMs can be useful for low-stakes testing or programming, when you need a different execution model or to mimic a specific hardware architecture

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig63.png "figure 6.3")
<br>**Figure 6.3**:  VM drawing by @_KtorZ_ 

Most dApps are architected with on-chain code and off-chain code. For a simple example, a dApp might track ownership of digital assets on-chain, but the actual transfer of the assets might occur off-chain, enabling for more efficiency, smaller transaction fees and less unnecessary data stored on-chain. 

Most blockchains offer some form of programmability, although with varying degrees of expressiveness. For example, **Bitcoin** does have a scripting language called *Script* which is not Turing-complete. While *Script*[^01] only allows you to program some basic tasks and operations, it can support complex solutions which sit on top of the base layer. It is more of a philosophical decision to do one thing very well (store of value) and there is a reluctance to make drastic changes to the protocol that may increase potential attack vectors. If you are familiar with Amazon Web Services, think of Bitcoin as kind of like Object Storage. 

Ethereum dApps are primarily coded in Solidity on-chain and Javascript off-chain. Ethereum follows an accounts-based model which is a different paradigm to Cardano. Initially there were two main programming languages​ for Cardano:
- Plutus - the primary platform to code dApps which interact with the Cardano blockchain
- Marlowe - a domain-specific language for building financial contracts.

We’ll cover both in this chapter, before exploring some of the more recent additions in the next chapter. 

## What is Plutus?

Plutus is a platform that offers a native smart contract language as well as the supporting infrastructure and tools to implement smart contracts on Cardano. ‘Plutus’ and ‘Haskell’ are often used interchangeably. You might hear someone say they code in Plutus, but they really mean they are coding in Haskell using the Plutus Framework.

The Plutus Framework enables developers to create *dApps* that interact with a *distributed ledger* featuring *scripting* capabilities. This is why it’s an entire platform, not just a language. It doesn’t just provide a few tools to make the bare minimum possible, it supports dApp development in its entirety, end-to-end from writing scripts, to testing, runtime support, and verification. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig64.png "figure 6.4")
<br>**Figure 6.4**: Plutus Platform drawing by @_KtorZ_

Plutus is a platform made of 3 main components:

- **Untyped Plutus Core (UPLC)** is the 'machine code' for the Cardano ledger
- **PlutusTx** is a plugin for compiling a subset of Haskell into UPLC to form the on-chain component of a contract application. 
- **Plutus Application Framework** is a collection of tools for writing smart contracts in Haskell

Plutus, Plutus Core, Untyped Plutus Core and UPLC are used interchangeably but all refer to the low-level on-chain machine language. 

To master Plutus, one must grasp three concepts:

- The Extended Unspent Transaction Output (eUTXO) model
- On-chain code, Plutus Core, which runs on the blockchain and is compiled by the Plutus compiler
- Off-chain code which runs on the user’s device. The Plutus Application Framework (PAF) may be used to write off-chain code, which is subsequently compiled by the GHC (Glasgow Haskell Compiler) 

Plutus smart contracts are essentially Turing-complete Haskell programs, with both on-chain and off-chain code written in Haskell. You can be sure that your smart contracts will be executed correctly if you follow best practice with Plutus. Haskell is the foremost purely functional programming language and builds on recent language research to create a secure, full-stack development environment. The rest of Cardano, for instance the node, is also implemented in Haskell whose strong static typing[^02] and relatively high expressiveness helps reduce common mistakes and ease the translation of complex requirements into programs. It ensures ‘the absence of side effects’ in mission critical code. 

To assist you with getting started, the Plutus Playground[^03] includes ‘how to’ guides and tutorials. To understand more about the Plutus language, you should read the Plutus explanations.[^04] If you want assistance when using Plutus, create an issue in the Plutus repository[^05] including as much information as possible.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig65.png "figure 6.5")
<br>**Figure 6.5**: Plutus off-chain and on-chain

**Plutus uses extended UTXO (eUTXO)**

Cardano employs the extended UTXO accounting model (eUTXO), which extends the UTXO model’s unspent (U) transaction (TX) output (O) accounting model (used by Bitcoin). A transaction in the UTXO paradigm contains inputs and outputs, with the inputs being unspent outputs from prior transactions. When an output is used as an input in a transaction, it is considered spent and cannot be reused. An address (a public key or public key hash) and a value are used to specify the output (consisting of an ada amount and optional, additional native token amounts).

eUTXO improves the UTXO architecture by enabling output addresses to include complicated logic that determines which transactions are allowed to unlock them, as well as by adding custom data to all outputs. Compared to other accounting models, this one has certain distinct benefits. The transaction’s success or failure is solely determined by the transaction and its inputs, not by anything else on the blockchain. As a result, before a transaction is transmitted to the blockchain, it may be validated for legitimacy off-chain. The transaction, on the other hand, is guaranteed to succeed if all inputs are still present.

**The workings of a Plutus transaction**

A transaction is a piece of data that has both inputs and outputs, and they may incorporate Plutus scripts. The unspent outputs from prior transactions (UTXO) are referred to as inputs. A UTXO gets spent as soon as it is used as an input in a transaction and cannot be used again. An address (a public key or public key hash) and a value are used to specify the output (consisting of an ada amount and optional additional native token amounts). This flow diagram provides a better understanding of the technical components of a transaction:

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig66.png "figure 6.6")
<br>**Figure 6.6**: Transaction inputs and outputs

In a nutshell, inputs are references to UTXOs introduced by earlier transactions, and outputs are the new UTXOs produced by this transaction. Since new data may be stored in the generated outputs, this enables the status of a smart contract to be modified.

Plutus Tx refers to parts of a Haskell program that are used to compile a contract application’s on-chain component into Plutus Core (this compiled code is then used for validating a transaction, hence the ‘Tx’). The Plutus Core expression that results may be included in transaction data or saved in the ledger. Plutus script refers to certain chunks of code that need specific processing on the blockchain. You can manage the flow of execution of a Plutus script by utilizing transactions. As a result, a transaction can be thought of as a series of messages sent to the smart contract. 

While assessing the off-chain code, the wallet should initiate a transaction. Once the transaction is submitted, it will be verified, and a validator node will analyze the Plutus code. Every node comes with a Plutus interpreter[^06] that is responsible for running script validators on-chain. The transaction will be deemed legitimate if the script evaluates correctly. The transaction will be denied otherwise.

The PAF may be used to write off-chain code, which is then compiled by the GHC (Glasgow Haskell Compiler), while the Plutus compiler compiles on-chain code (written in Plutus Core). It’s critical to grasp the link between these Plutus principles and native tokens functionality to realize how the latter becomes a more powerful feature as a result of their interaction.

**Plutus Core**

Plutus Core is utilized to build the eUTXO paradigm. Plutus Core scripts may be written in a concise, functional language comparable to Haskell, and a significant portion of Haskell can be leveraged. You don’t write Plutus Core as a smart contract programmer; In practice, you’ll create validator scripts in Haskell, which will be automatically compiled into Plutus Core using a GHC (Glasgow Haskell Compiler) plug-in called Plutus Tx.[^07] These scripts will be run ‘live’ on the chain by nodes during transaction validation. They will either use validator scripts[^08] to unlock UTXOs, or minting policies to regulate the minting and burning of native tokens. 

**Plutus Application Framework (PAF)**

Validator scripts’ on-chain status can only be changed by transactions that spend and create script output. When designing a Plutus application, both the on-chain (the Plutus Core scripts) and the off-chain (the transaction building and submission) components must be taken into account.

Unlike Ethereum, where the on-chain code is mostly written in Solidity and the off-chain code is written in JavaScript, the Cardano off-chain code is written in Haskell, exactly like the on-chain code. The business logic[^09] will only have to be written once this way. The validator script and the code that creates the transactions that execute the validator script may then employ this reasoning.

Many applications need to monitor the UTXO set[^10] for changes to certain addresses, so if the contract is written as a state machine,[^11] you need to keep track of the unspent output, which reflects the machine’s current state, and update your local state if the on-chain state changes. Many applications need communication with the wallet backend to access the crypto funds they are using for transactions. The Plutus Application Framework (PAF) makes it simple to access services that are often used by Plutus apps. 

**Plutus Application Backend (PAB)**

The Plutus application backend, which offers runtime support for access to the blockchain as well as additional concerns like persistence, logging, and monitoring, may be used to execute applications built using the framework’s libraries. Applications built on top of the PAF provide an HTTP and WebSocket[^12] interface that allows users to interact with the app from a web browser.

The Plutus off-chain component is executed by the PAB, which is constantly iterated upon with each release. It handles wallet backend and node application requests, saves application state, and provides an HTTP API for managing application instances. 

**Native tokens and Plutus**

With the Mary hard fork in February 2021, native tokens became accessible on Cardano. Tokens could now be created by anybody, and they can be transferred and received freely. 

Each native token has its own minting policy,[^13] which specifies the circumstances under which tokens may be minted and burned. Users create minting policies in Haskell and compile them to Plutus Core after Plutus was deployed. During the minting or burning process, the Plutus Core policy script will be run in the context of the transaction, and it will have to approve or reject the action. This feature has boosted Cardano Non-Fungible Tokens (CNFTs) adoption by allowing for the use of considerably more complicated minting policies and trustless NFT issuance.

Minting policies are made up of a series of basic rules that define signatures and timelocks. For example, a policy may declare that transactions can only mint or burn tokens if they are signed by two of the five potential signatures. A different policy can allow minting only before or after a certain time.

**Plutus Virtual Machine**

Most people have heard of the Java virtual machine (JVM) which enables a computer to execute Java programs but also programs written in other languages that are also compiled to Java bytecode.

Similarly, there is also the Plutus Virtual Machine (known as Plutus VM). Smart contracts don’t access your computer’s resources directly like other programs on your computer. It would increase the security risk considerably to grant such access. VMs are well suited for running smart contracts as they offer a safe execution environment with safeguards and custom features. For smart contracts, it’s important a VM can measure resource usage accurately. 

In the case of Cardano, the VM's machine code is Untyped Plutus Core. UPLC is a polymorphic lambda calculus with some addons. For now, just know that Lambda calculus is a notation for describing mathematical functions and programs, while polymorphic relates to the ability to use the same interface for different underlying data types.

Plutus VM’s ‘cost model’ is measured with two metrics: steps and memory. Every Plutus instruction has a specific cost tied to it. The execution cost is measured by the number of steps the VM needs to take and the amount of memory it requires. Each version of Plutus has its own cost model, with its configuration stored as part of the protocol parameters which can be updated. This enables us to have an accurate idea of the cost of execution of any Plutus program. This is worlds apart from fees on Ethereum which can go up and down like a yo-yo.

There are other benefits, for example, the Plutus virtual machine can stop a program that goes above its authorized budget. Developers can also use the VM for realistic simulations of how smart contracts will behave, closely mirroring real world ledger conditions. Remember, with the eUTxO model, execution happens locally, there's no global state like with Ethereum. This all adds up to the Plutus VM being completely deterministic. Developers don’t like surprises with their code. Plutus is predictable and reproducible. 

**Strengths of Plutus**

Plutus offers significant security benefits. It provides a simpler, more reliable method of demonstrating that your smart contracts are accurate and will not experience the issues that have plagued prior smart contract language designs.

Plutus allows for a new integrated approach to smart contract and distributed application development that is easier and more secure than prior options. The same language is used for both on-chain and off-chain programming. You employ a common code base, which the Plutus toolchain[^14] divides into on-chain and off-chain code and packages for deployment. Plutus also enables user-defined tokens (both fungible and non-fungible) natively, which needs much less code than Ethereum.

A key differentiator of eUTXO, and Plutus, is its predictability, often referred to as determinism. At ScotFest,[^15] James Aman (CTO of Topl) coined the phrase:

>‘Not your output, not your outcome’ because if you want a thing to happen in the world, you need the output, the actual thing that goes into state, to reflect your desire… because those outputs then help you achieve your desired outcomes 

## Plutus Scripts

Cardano validates operations via scripts. Pure functions with True or False outputs are implemented in these scripts. The process of invoking the script interpreter to run a script with relevant arguments is known as script validation. A script is code that determines if the transaction spending the output is approved. This kind of script is known as a validator script since it checks if the transaction is permitted. A simple validator script would verify whether the spending transaction was signed by a certain key, just as basic pay-to-pubkey outputs do. Scripts may be used to express meaningful logic on the chain. Metadata and scripts are bundled together in a single transaction for greater throughput.

The eUTXO paradigm operates by passing three parameters to validator scripts:

- **Datum**: This is a piece of data that is linked with the output and is locked by the script (just the hash is present). This is usually used to carry state.
- **Redeemer**: a piece of info associated with the spending input. This is usually used to provide the spender’s input to the script
- **Context**: this is the metadata concerning a spending transaction. This is used to make assertions about how the output is sent. The context can be made up of inputs (outputs from previous transactions to be spent), reference inputs (just for ref, not to be spent), new outputs, fees, minted values, certificates, reward withdrawals, date ranges, transaction signatures, redeemers, map of datum hashes, transaction IDs).

**Simple example**  

A customer ‘John’ wants to buy ‘Cardano for the M₳sses’ which costs ₳10. There must be confirmation they have enough ₳ in their wallet before they can buy it.

```
if EnoughADA(book=CardanoForTheMasses, customer=john):
    buyBook()

def EnoughADA (book,customer):
    return customer["balance"] >= book["bookPrice"]

def buyBook():
    print ("You have enough ADA to buy the book")

CardanoForTheMasses = {"bookPrice":₳10}
john = {"balance":₳11}
```

In the above example:

The datum is the information about this transaction: *john.balance*
The context is the state of the world, the price of the book for this example: *CardanoForTheMasses.bookPrice*
The redeemer, is the action to perform: *buyBook()*

The validator script is the function that uses all that information, in this example, *EnoughADA*

GitHub contains examples of validator scripts on every smart contract: 

- Plutus transaction tutorial[^16]
- Plutus Hello World[^17]
- Plutus pioneers English Auction[^18]

**Cost model parameters**

A number of parameters in the cost model for Plutus Core scripts are also included in the Cardano protocol parameters. Individual settings may be tweaked by developers.

See the following for more details:

- A list of cost model parameters and their brief description[^19]
- Sources to find out more about the meaning of parameters[^20]

## Plutus Versions

Cardano, like any other blockchain, is a decentralized ledger or database that keeps track of all transactions and blocks made on the network. This database distributes records with all participants and synchronizes with blockchain activity on a regular basis to deliver transparent and up-to-date data to anybody. In layman’s terms, a ledger is just a system that tracks who owns what.

Cardano DB Sync[^21] retrieves such blockchain information and lets users run CLI commands to access transaction and block details. There are now many alternatives to DB Sync such as Marconi,[^22] Carp,[^23] Kupo,[^24] etc. Another is Ledger Sync[^25] which is written in Java, open sourced by the Cardano Foundation, and puts sequential blockchain data in an easily accessible database structure. You can use the Cardano Explorer[^26] – a graphical user interface that exposes information in a straightforward manner – for more easy and user-friendly data analysis. 

Before a transaction is submitted to a block,[^27] it is validated by a block producer. To avoid double-spending, the sender must have adequate funds, and all nodes across the ledger must establish consensus. Let’s look at how this worked in the Shelley ledger, and how Plutus scripts changed it to enable multi-asset transactions and smart contracts.

**Transaction validation before Goguen**

Before Plutus scripts were introduced in the Goguen era, there was a simple *‘Native Script’* scripting language. When an output is used as an input in a transaction, it is considered spent and cannot be reused. The following are the parameters for the output:

- an address which holds a payment credential and an optional stake credential, which may be either a public/verification key hash or a script hash. The stake credential might alternatively be a link to the registration certificate.
- a value: this is the amount of ada that may be spent.

The owner of the private key (also known as the signature key), which corresponds to the payment credential supplied in the address, must sign a transaction. Only ada transactions were supported before Goguen. The Shelley formal specification introduced the idea of multi-signature (multisig) scripts, which are captured wholly by ledger rules. If a predetermined combination of signatures is given, this multisig approach allows an unspent transaction output to be used as an input to a new transaction. 

For example, if two people must sign the transaction at the same time, two out of three keys must be given, and so on. Multisig is a very simple language that enables you to interact with RequireSignature, RequireAllOf, RequireAnyOf, and RequireMOfN, among other constructors. CIP-1854[^28] contains more info about these scripts, as well as the *Formal Ledger Specification, Figure 4: Multi-signature via Native Scripts*[^29]

**Alonzo (Plutus V1)**

With the introduction of multi-asset support and smart contracts on Cardano, upgrading the fundamental multisig scripting language with more complex options was required. As part of the Alonzo upgrade, IOG implemented the required tools and infrastructure, as well as support for a new programming language called Plutus Core.

The Alonzo ledger employs the extended unspent transaction output (eUTXO) paradigm to upgrade multisig to Plutus Core to give strong scripting features.

Alonzo made the following adjustments to the ledger data:

1. Plutus scripts can lock UTXOs.
2. Script state-like functionality was enabled via a new component added to the contents of the output pieces of UTXOs. A UTXO locked by Plutus scripts includes a datum in addition to assets and an address. A datum is a piece of information that represents an interpretation of the script state.
3. A number of new protocol parameters were added to enforce extra transaction validation requirements. These include upper restrictions on how much processing power scripts may use.

Transactions were updated to support Plutus scripts as follows:

1. The transaction now had a redeemer, which is a user-specified parameter for each of its activities. A redeemer may fulfill a variety of functions depending on the script. It may, for example, serve as the user’s decision to ‘hit’ or ‘stand’ in a game of blackjack or a ‘like’ or ‘share’ in some utopian decentralized social media dApp.
2. The transaction defines each script’s computational execution budgets.
3. Alonzo leverages collateral to verify that a transaction can pay its execution cost
4. Transactions include an integrity hash, which is used to confirm that it hasn’t been tampered with, hasn’t expired, and so on.

The node runs Alonzo-specific tests to guarantee that the transaction is built successfully. It must not, for example, exceed the maximum execution resource budget. It also runs the scripts by using Plutus script interpreter.

Ethereum’s non-deterministic ‘gas’ model has the potential to charge consumers extortionately high fees. This form of indeterminism is addressed in Cardano scripts by requiring that both the resource budget and the fee necessary to cover it be included in the transaction. When designing a transaction since the Alonzo upgrade, a user may now forecast both locally. Script execution will always return one of two values: True or False, and it will not loop endlessly. This is because every action a script does requires a non-zero amount of resources, which the interpreter keeps track of. If the transaction’s budget is exceeded, the script is terminated and False is returned.

The following critical features help to forecast the results of script and transaction validation:

- When applied with the same parameters, the script interpreter will always terminate and deliver the same validation result
- During validation, a transaction should correct all variables provided to the script interpreter
- A transaction enumerates all of the operations it performs that need script validation
- A transaction’s mandatory signatures guarantee that it can’t be tampered with by an attacker in a manner that causes scripts to fail.

In the eUTXO ledger paradigm, implementing a transaction is deterministic.

**Vasil (Plutus V2)**

There were three Cardano Improvement Proposals implemented with the Vasil hard fork to enhance the way Plutus operates, to make things easier for developers. All three dovetail together and complement each other. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/seba.png "Seba tweet")

CIP31[^30] defined **reference inputs**, a major step forward for how developers interact with UTXOs. A reference input is a transaction input associated with a specific transaction output, however, rather than spending the output, it just references it. 

A datum can be thought of as the data for your script, bits of data attached to outputs, where you might store data like a user handle, or avatar etc. Before Vasil, if you wanted to read your handle, or score of a soccer match etc., in your dApp, you had to consume the UTXO and then recreate it after you had read the datum.

Reference inputs allow you to read the datum, or the data that’s stored at a UTXO, without consuming it and recreating it. This means that multiple dApps can read from the same datum simultaneously. This boosts concurrency and throughput dramatically.

Ergo, pioneers in the UTXO space, already introduced a similar concept called ‘data inputs’[^31] in 2020.

CIP 32 defined **inline datums**. Before Vasil, this high score, or other data from the datum wasn’t stored on-chain. The hash (fingerprint) of it was stored on-chain and it was up to the developer to include it when they were interacting with the script. Since Vasil, the data can be stored on-chain, eliminating the need for hashes and moving closer to a truly decentralized architecture.

CIP 33 is about **reference scripts**. Plutus script references can be linked to transaction outputs, allowing them to be stored on-chain and reused later. It means you are no longer required to provide a copy of the script with each transaction, thereby reducing developer friction. Using the same script in several transactions decreases transaction sizes, boosts throughput and lowers script execution costs.

Before Vasil, developers had to share the scripts offline so that they could be included in transactions. However, it was harder to share those scripts with different people so that they could interact with their dApp. 

Reference scripts allow developers to put Plutus scripts on-chain and then, rather than include them in a transaction, they can instead include a pointer in the transaction that just references that script on the existing chain. That means that a user doesn’t need to have a copy of this script to interact with it. You just need to let people know the address it’s at, and then users anywhere can use the same script and point to it. 

This enables a use case where a developer can put reference scripts on-chain and allow others to use them as a library. There could be several libraries considered to be core to Plutus, and IOG will put them where anyone can use them and then publish the address. This allows anyone in the ecosystem to take libraries and make them available to the wider public, a powerful enhancement. 

Looking at all three CIPs holistically, these enhancements pushed Plutus forward and make developers' lives easier. IOG is putting more on-chain, freeing developers from the need to monitor scripts and share scripts and datums and increases concurrency by allowing users to interact with UTXOs.

**Valentine Hard Fork** 

Known internally as the SECP (Standards for Efficient Cryptography protocol) update, CIP 49[^32] was implemented as the ‘Valentine’ Intra-era hard fork[^33] on 14th February 2023. 

Cryptographic primitives are like the Lego blocks used to create secure transactions and develop algorithms when building dApps. They can be random number generators, entropy (randomness) sources, basic memory or math operations that are required by the cryptographic algorithms. 

Before we go any further, let’s unscramble some of the terminology:

*Elliptic Curve Digital Signature Algorithm* or *ECDSA* is a cryptographic scheme for producing signatures using public and private keys. It uses a variant of Schnorr signature based on twisted Edwards curves. So what is a Schnorr signature? 

A *Schnorr signature* is a digital signature produced by the Schnorr signature algorithm that was described by Claus Schnorr. It is known for its simplicity, efficiency and for generating short signatures.

*Secp256k1* is the name of the elliptic curve used by Bitcoin, Ethereum and others to implement its public key cryptography. Whereas Cardano, Monero, Ripple and others employ *edwards25519* elliptic curve as a basis for their key pair generation. The curve comes from the *Ed25519* signature scheme.

Initially, the Vasil hard fork was to add built-in support for *secp256k1* on Cardano, enabling developers to interact with signatures from those other blockchains. However, after extensive testing, it was decided to omit this enhancement from Vasil. As this upgrade impacted the Plutus interpreter, it needed to be implemented as a hard fork. After Vasil, it was decided that future updates would only be scheduled if certain critical mass indicators were met. A set percentage of SPOs would need to be running the new node. Exchanges would need to be consulted. Impact to other Cardano components would need to be assessed. Cexplorer.io/versions is a good page to track for ‘hard fork readiness’.

The changes, outlined in CIP 49, enable dApp developers to effectively build cross-chain applications with bridges, sidechains and wrapped assets. The new functionality is crucial for bridges to sidechains, and other interoperability solutions like Wanchain.[^34] These primitives are supported as built-in functions native to Cardano, implemented and audited by security experts. This gives Plutus developer more options. For example, Schnorr-based designs are well established and adopted by the wider dApp community.

As is often the case with Cardano, an analogy helps understanding. Emmanuel (@thepizzaknight_)[^35] provided this New Year’s Day gift:

> For the purposes of this thread, regard Crypto Primitives as real-world language families, let's use the Indo-European language family. Cardano uses Curve25519, think Germanic (English, Deutsche, etc) Ethereum, Bitcoin, etc. use SECP256k1, think Romance (French, Spanish, etc).
>
>As you can imagine, it can be tough to do business as an English speaker with a Spanish-speaking person. You have to hire translators and go through a lot just to get work done. This is what it's like now for dApp (and Bridge) builders on Cardano trying to go cross-chain. Thankfully the next Chain Upgrade Event fixes this by adding support for SECP256k1 as a Built-in function on Cardano (think of it as adding a new DNA strand). This will allow Cardano (English) to naturally understand other chains (Spanish). What does this mean for you as a user or a builder? New cross-chain opportunities with better bridges and access to new tokens and dApps from other chains. With the Sidechain strategy, Cardano needs this improvement for its Interoperability vision to be feasible and real. 

**Backwards compatibility** 

The Cardano Ledger tags scripts with a language (V1 for Alonzo, V2 was Vasil). This dictates how the ledger treats the script. Plutus V1 must remain the same forever, or else anyone could manipulate existing scripts, potentially making outputs un-spendable and breaking users’ assumptions. For this reason, if Plutus needs significant updating, a ‘new’ language in the ledger is required. 

Generally, each hard fork will produce a new ‘Plutus language version’ with additional functionality. From the ledger’s perspective, they are completely unrelated and there is no requirement that they be similar in any way. Your old scripts are still valid and will function as before. You are not obligated to use the new language version, which is a superset of the prior version. You obviously need to tag your script with the correct version to avail of new features, see ‘language versions’ in the docs for more details.

To understand what kinds of changes require a new language version, see CIP 35–Plutus Core Evolution.[^36] 

**Plutus V3**

Throughout 2023, the Plutus team worked on increasing script capacity with plutonomy,[^37] an optimizer for untyped plutus core. This is part of the implementation of ‘sums-of-products’. This will be a change to the Plutus Core language, which is expected to happen at the next hard fork, Chang, in 2024. This update will add native support for datatypes and provide performance improvements to scripts. Read this CIP-85[^38] to learn more. Michael Peyton Jones (Technical Architect at IOG):

>This CIP proposes a substantial extension to Plutus Core to support sums-of-products, with the aim of realising some substantial performance improvements.

Crucially, Plutus V3 will also support built-in functions for BLS12-381 curves.[^39] A BLS (Boneh–Lynn–Shacham) digital signature allows a user to verify that a signer is authentic. BLS support will bring 15+ crypto primitives to Plutus enabling the ability for zero knowledge rollups. In addition to that, new built-ins for *Keccak-256*[^40] will enhance compatibility with Ethereum. The Plutus team is working to improve the onboarding experience with a new Quick start guide.[^41]

As we will see later, the next hard fork promises to be a big update, as it will also be a milestone with the introduction of on-chain governance mechanisms. It was the ‘most awaited feature’ from the 2023 Cardano Developer Ecosystem Survey[^42] 

>The anticipation within the Cardano community is palpable, especially concerning the forthcoming Plutus V3, which is expected to bring groundbreaking advancements in zero-knowledge cryptography for Cardano. This feature tops the list of most-awaited developments, underscoring the community's keen interest in more sophisticated and privacy-preserving cryptographic techniques.

## Plutus Tools

Developers can leverage a variety of tools to assess and implement smart contracts on Cardano. 

Plutus Playground

The Plutus Playground is a place where smart contracts may be written and tested before being put on the Cardano blockchain. It’s a web-based platform for Plutus development with modest resource consumption. The Plutus Playground offers a web-based simulator for building and executing smart contracts, as well as access to popular smart contracts that have already been developed. 

There is no need to install anything to use the Plutus Playground, which can be accessed from a web browser. The user interface is divided into three parts:

- editor
- simulator
- transactions

The simulator displays how a contract will function on Cardano. One of the key parts of this is that it can be used as a teaching tool for beginners. The wallets that interact with a contract, as well as the actions that affect the result, may be defined and updated by users. The outcomes may then be analyzed to determine what occurs on the blockchain and how transactions take place. Visit the Plutus github repository or watch the Plutus application compiling and testing tutorial[^43] for further details.

**Plutus Application Backend**  

The Plutus Application Framework (PAF) includes the Plutus Application Backend (PAB), which is the off-chain infrastructure in the UTXO paradigm that produces the transactions that power the dApps. Because it has to look at the ledger state, take some information from the ledger, and put it all together to produce a transaction with the proper bits of data in the right location, this off-chain architecture is somewhat complex. The PAB is a Haskell library that simplifies the development of both off-chain infrastructure and on-chain scripts.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig67.png "figure 6.7")
**Figure 6.7**: A high-level architecture of the Plutus Platform, with an emphasis on applications. From plutus.readthedocs.io/

In this diagram, the Platform breaks down based on which part of the system we’re interested in:
- Plutus Foundation[^44] is there to support writing the trusted kernel of code, and executing it on the chain
- The Plutus Application Framework is for writing Plutus dApps

The following components must be present in addition to the PAB:

- **Chain index**: a database of information obtained from Cardano transactions. It must be co-located with a Cardano node and utilizes the Cardano node’s chain sync protocol. The PAB’s chain index is a read-only component. As a result, a single instance of the chain index may be shared by several instances of the PAB. A HTTP API is used to serve all chain index requests
- **Cardano node**: the PAB leverages a socket protocol to subscribe to ledger changes from the node.

While not mandatory for dApp creation or implementation, the PAB is a useful Cardano tool that makes developing dApps easier, safer, and more cost-effective. It relieves developers of mundane duties by offering information from relevant sources in an accessible style. As the ecosystem matures, the community are developing their own tooling and API-based alternatives.[^45]

Innovative new platforms like Genius Yield (geniusyield.co) are trailblazers for Plutus, creating custom PAB alternatives that are open source, available to other builders. Dr Lars Brünjes, Chief Technology Officer (IOG Education Director and Genius Yield CTO) talked about open-source ethos in a *Learn Cardano* interview:[^46]

> It's one of my pet hates, I can't understand how you can possibly NOT make it open source. I mean, the whole point of smart contracts…when I explain to somebody what a smart contract is….you always say ‘with normal human contracts, there's always ambiguity, and legal issues and you replace that with mathematics and code, and so it's crystal clear what’s what’   …but this whole point is mute if you don't make your smart contracts public, because then nobody can check the actual logic. I mean then you can just as well forget about blockchain and do it centralized. So in my opinion, you have to at least make the smart contracts public… and this PAB replacement that we mentioned a couple of times now, we definitely also want to make it open source, so that everybody can profit from it, and not every project has to reinvent that over and over again.

**Plutus fee estimator**  

IOG performance specialists created the Plutus fee calculator as an in-house tool for pricing benchmarking and comparison. It predicts the fees that will be charged for a transaction using data from real-world Plutus transactions. The estimator may be used to estimate costs for individual script transactions or whole dApps before or during development, as well as to compute fees for existing transactions (e.g., to assess the fees that will be charged if network parameters change). 

The Cardano ledger’s design principles enable great performance while maintaining stringent security standards. The Extended Unspent Transaction Output (eUTXO) accounting model allows for Cardano transactions and scripts to be checked locally (off-chain), enabling users to see whether a transaction is legitimate before executing it on-chain and incurring fees. Furthermore, transaction fees are fixed with no surprises. For comparison, the cost of executing a smart contract on Ethereum varies based on network traffic, ranging from $5 to hundreds[^47] of dollars. Even unsuccessful Ethereum transactions may incur fees, adding to the price unpredictability.

Users on Cardano, on the other hand, may assess the transaction fees in advance. There is no need to pay for a transaction that may fail since the user knows whether the transaction is legitimate or not in advance. This prevents money from being wasted and eliminates on-chain failures. Cardano’s ada execution fee is always consistent because it is based on predetermined network protocol parameters rather than, for example, varying network congestion variables.

Cardano’s pricing strategy is based mostly on market demand rather than real supply, both relative and absolute price[^48] must be considered. One means of doing this is by examining the implications of smart contract pricing, non-fungible token (NFT) activities, and other factors with regard to a common value — in this example, the use of Cardano’s processing power. 

Smart contract pricing in Cardano is based on a fixed cost, which is determined by the price of used resources (UTXO size or computation/memory consumed while executing). Stake pool operators’ (SPO) labor and resources that verify network transactions must be adequately compensated with fees. Furthermore, ensuring that any method of adopting Cardano is not significantly less expensive than another helps to prevent a wide range of adversarial attacks (e.g. a DDoS attack).

Flexibility is also a significant characteristic of the Cardano protocol, since it allows users to adjust their settings and respond to price swings. If the value of ada rises dramatically, protocol settings may be modified if necessary to avoid the user from overspending for smart contract execution.

IOG created the Plutus fee estimator tool for pricing benchmarking and comparison. The estimator may be used to estimate costs for individual script transactions or whole dApps before or during development, as well as to predict fees for existing transactions. It might also be used to see how script updates or optimizations affect costs.

Test Drive the Plutus fee estimator[^49] and see how easy it is to estimate the processing fee without saying goodbye to your funds if a transaction fails.

**Cooked Validators**

With the *cooked-validators* library, you can write off-chain code and obtain property-based testing for free. As a Haskell developer using formal methods, you should be devoted to using tools and procedures to ensure the safety and soundness of decentralized applications (dApps). Just writing and deploying a dApp is inadequate; all on-chain code and Plutus scripts should be carefully tested against a variety of bad actors.

With this in mind, *Tweag* introduced *cooked-validators*,[^50] a collection of ready-to-use tools for working with Plutus validator scripts. This library aids in the implementation of the innermost layer of off-chain code, which is responsible for transaction generation and submission. You receive property-based testing at the transaction level for free by using this library.

You may verify various safety and correctness aspects of your on-chain code by utilizing cooked-validators to create your off-chain code, which can considerably boost your trust in the code’s correctness. During an audit, this may save time and money. The first step in a Tweag audit is to leverage cooked-validators to write transaction-generating code, allowing them to interact with their client’s infrastructure.

## Writing Plutus transactions






![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig68.png "figure 6.8")

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig69.png "figure 6.9")

**_To be uploaded soon..._**


[^01]: Bitcoin Script, en.bitcoin.it/wiki/Script
[^02]: **Static typing** means that before source code is compiled, the type (integer, floating point, string, etc) associated with every variable must be known. Compile time is when the programming code is translated to machine code. Runtime is when a program is running, ie. after compile time.
[^03]: Plutus Playground, playground.plutus.iohkdev.io/
[^04]: Plutus explanations, plutus-apps.readthedocs.io/en/latest/plutus/explanations/index.html
[^05]: Plutus github repo, github.com/intersectMBO/plutus
[^06]: An **interpreter** translates code from a high-level programming language into machine code line-by-line as the code runs
[^07]: Plutus Tx: The libraries and compiler for compiling Haskell into Plutus Core to form the on-chain part of a contract application.
[^08]: Validator scripts, docs.cardano.org/plutus/Plutus-validator-scripts
[^09]: **Business logic** or domain logic is the part of the program that encodes the real-world business rules that determine how data can be created, stored, and changed. It is contrasted with the remainder of the software that might be concerned with lower-level details.
[^10]: The **UTXO set** is the comprehensive set of all UTXOs existing at a given point in time. The sum of the amounts of each UTXO in this set is the total supply of existing currency at that point of time. Anyone can verify the total supply at any time in a trustless manner.
[^11]: A finite-state machine (FSM) or simply a **state machine**, is a mathematical model of computation. It is an abstract machine that can be in exactly one of a finite number of states at any given time. The FSM can change from one state to another in response to some external inputs and/or a condition is satisfied; the change from one state to another is called a transition. An FSM is defined by a list of its states, its initial state, and the conditions for each transition.
[^12]: **WebSocket** is a communications protocol, providing full-duplex communication channels over a single TCP connection.The Transmission Control Protocol (TCP) is one of the main protocols of the Internet protocol suite. It originated in the initial network implementation in which it complemented the Internet Protocol (IP). Therefore, the entire suite is commonly referred to as TCP/IP.
[^13]: Minting policy, github.com/input-output-hk/cardano-documentation/blob/staging/content/07-native-tokens/01-learn.mdx#minting-policy
[^14]: A **toolchain** is a set of programming tools that is used to perform a complex software development task or to create a software product, which is typically another computer program or a set of related programs. 
[^15]: The UTXO Alliance, youtube.com/watch?v=j-Mil0RcKhQ
[^16]: Plutus transactions model, github.com/input-output-hk/Alonzo-testnet/blob/main/Alonzo-tutorials/Plutus_transactions_tutorial.md#transaction-to-lock-funds
[^17]: Plutus HelloWorld, github.com/input-output-hk/Alonzo-testnet/blob/e27563ec0c0c3723376f4d12881cd003a7a7157f/resources/plutus-sources/plutus-helloworld/src/Cardano/PlutusExample/HelloWorld.hs#L47
[^18]: EnglishAuction.hs, github.com/input-output-hk/plutus-pioneer-program/blob/024ebd367bf6c4003b482bfb4c6db7d745ec85aa/code/week01/src/Week01/EnglishAuction.hs#L103
[^19]: Cost model parameters, plutus.readthedocs.io/en/latest/reference/cost-model-parameters.html
[^20]: Plutus bibliography, plutus.readthedocs.io/en/latest/reference/bibliography.html#id13
[^21]: The purpose of **DB Sync** is to follow the Cardano chain and take information from the chain and an internally maintained copy of ledger state. Data is then extracted from the chain and inserted into a PostgreSQL database. SQL queries can then be written directly against the database schema.
[^22]: Marconi, github.com/input-output-hk/marconi
[^23]: Carp -  New Cardano SQL indexer & replacement for db-sync, medium.com/dcspark/carp-new-cardano-sql-indexer-replacement-for-db-sync-b990243a329e
[^24]: Kupo, github.com/cardanosolutions/kupo
[^25]: Accessing Cardano Blockchain Data with Ledger Sync, cardanofoundation.org/en/news/accessing-cardano-blockchain-data-with-ledger-sync/
[^26]: CF Cardano Explorer, github.com/cardano-foundation/cf-explorer/releases/
[^27]: Cardano Nodes, docs.cardano.org/new-to-cardano/cardano-nodes
[^28]: CIP-1854, github.com/cardano-foundation/CIPs/tree/master/CIP-1854
[^29]: Shelley Ledger spec, github.com/input-output-hk/cardano-ledger/releases/latest/download/shelley-ledger.pdf
[^30]: CIP (Cardano improvement proposals), cips.cardano.org/
[^31]: Ergo data inputs, docs.ergoplatform.com/dev/scs/data-inputs/
[^32]: CIP 49: ECDSA and Schnorr signatures in Plutus Core, github.com/mlabs-haskell/CIPs/blob/c5bdd66fe49c19c341499f86cebaa2eef9e90b74/CIP-0049/README.md
[^33]: **Intra-era hard fork** is a small and focused semantic change to the ledger requiring a hard fork.
[^34]: Wanchain, the Wide Area Network chain, is an interoperability solution with a mission to drive blockchain adoption through cross chain interoperability by building fully decentralized bridges that connect siloed blockchain networks
[^35]: thepizzaknight_ primitives analogy, twitter.com/thepizzaknight_/status/1609373418759012353?s=20&t=2BonGRIWcKofrMSWJe4qYg
[^36]: CIP 35–Plutus Core Evolution, cips.cardano.org/cip/CIP-0035
[^37]: Plutonomy, github.com/well-typed/plutonomy#readme
[^38]: CIP - 0085 Sums-of-products in Plutus Core, github.com/cardano-foundation/CIPs/pull/455
[^39]: Plutus V3, github.com/IntersectMBO/cardano-ledger/pull/3365
[^40]: Keccak-256 is a hashing algorithm within Solidity and stems from the SHA-3 family.
[^41]: Plutus quick start, plutus.readthedocs.io/en/latest/quick-start.html
[^42]: State of the Cardano Developer Ecosystem - 2023, cardano-foundation.github.io/state-of-the-developer-ecosystem/2023/
[^43]: Plutus Playground - Video Tutorial: Compiling and testing a Plutus App, youtube.com/watch?v=DhRS-JvoCw8
[^44]: Plutus Foundation, plutus.readthedocs.io/en/latest/explanations/plutus-foundation.html#what-is-plutus-foundation
[^45]: API alternatives, youtu.be/W2R3zl91U24?t=357
[^46]: Learn Cardano Interview w/ Genius Yield, youtube.com/watch?v=7KBhfe6GVAA&t=1763s
[^47]: Ethereum Gas Fees Continue to Rise, analyticsinsight.net/ethereum-gas-fees-continue-to-rise-while-bitgert-zero-gas-fee-blockchain-is-booming/
[^48]: ​​**Absolute vs. Relative Price**: Absolute price is the number of dollars that can be exchanged for a specified quantity of a given good. Relative price is the quantity of some other good that can be exchanged for a specified quantity of a given good. Suppose we have two goods A and B. The absolute price of good A is the number of dollars necessary to purchase a unit of good A. The relative price of good A in terms of B is the amount of good B necessary to purchase a unit of good A. 
[^49]: Plutus Fee Estimator, docs.cardano.org/cardano-testnet/tools/plutus-fee-estimator
[^50]: Cooked validators, github.com/tweag/plutus-libs/tree/main/cooked-validators
[^51]:
[^52]:
[^53]:
[^54]:
[^55]:
[^56]:
[^57]:
[^58]:
[^59]:
[^60]:
[^61]:
[^62]:
[^63]:
[^64]:
[^65]:
[^66]:
[^67]:
[^68]:
[^69]:
[^70]:
[^71]:
[^72]:
[^73]:
[^74]:
[^75]:
[^76]:
[^77]:
[^78]:
[^79]:
[^80]:
[^81]:
[^82]:
[^83]:
[^84]:
[^85]:
[^86]:
[^87]:
[^88]:
[^89]:
[^90]:
[^91]:
[^92]:
[^93]:
[^94]:
[^95]:
[^96]:
[^97]:






