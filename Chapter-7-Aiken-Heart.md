# Chapter 7: Aiken ❤️

*‘I am a simple man and I want simple answers’* ― Howard Aiken

**TO DO: add markdown format**

A much perpetuated myth is that you must learn Haskell to write smart contracts on Cardano. Let’s zoom out for a moment, to understand the bigger picture. Haskell programs, coded on the Plutus Platform, do indeed compile to Untyped Plutus Core (UPLC) and while the Cardano ledger only understands Plutus Core, this low-level machine language is not something developers code in day to day. So while you can use Haskell exclusively if you want, the reality is UPLC is an easy compilation target for most functional programming languages. The standard features of such languages are a good match for Cardano’s eUTxO model, where UTxOs are immutable. You can choose from a growing list of high-level languages which compile to UPLC. 
It is the UPLC component which is key to understanding how Aiken functions. It provides us with determinism and a strong security. Developers like predictable, reproducible settings and Aiken builds on these foundations with a friendly developer experience and short iteration times. It's a joy, in this regard, as many developers have testified.

Figure 7.1: Smart Contracts Programming on Cardano drawing by @_KtorZ_ 
That’s enough to give you context of the low-level intricacies, the rest of this chapter will focus on the top left of the drawing, the high-level languages available on Cardano. Most developers prefer these languages as they can express business logic easily with a rich vocabulary, and the code is generally more readable and optimized for audits and static analysis.

Helios is a Domain Specific Language (DSL) that compiles to Plutus-Core. It is a new language built from the ground up with Cardano in mind. Helios is also a functional language but is very similar to TypeScript. Notably, Helios’s compiler is just a single javascript file with no external dependencies to any library, so the Helios team has kept control of their ecosystem. The flip side is everything must be built from scratch, and this takes time for the language APIs, SDKs and tooling to mature. Helios is geared for building client applications in the browser but is also easy to use from within a javascript project.  

OpShin is an implementation of Cardano smart contracts written in a strict subset of normal Python. It enables you to write smart contracts in completely valid, albeit restricted Python3. OpShin implements its own type system and compile-time checks to ensure correctness. Python packages for UPLC and pluto have been made available for anyone that wants to build UPLC tooling in Python. 

Interestingly, Algorand has adopted a similar strategy that hinges on the benefit of using normal Python, which brings with it all the features that come with developing on Python such as widespread editor support, language servers, linters, testing frameworks and verification tools. 

Plutarch is a typed eDSL (embedded domain specific language) in Haskell for writing efficient Plutus Core validators. It is not a new language, it’s just good old Haskell with no restrictions. Some say Plutarch is the language PlutusTx could have been, with no Template Haskell involved. Axo, a decentralized exchange on Cardano, was built with Plutarch. 



From the 2023 Cardano Developer Ecosystem Survey

Meanwhile, Plutarch appears to find its niche among more seasoned developers, suggesting its appeal might be rooted in advanced features or complexities that cater more effectively to those with extensive backgrounds. This dynamic illustrates a vibrant and responsive ecosystem, with innovative tools emerging and developers open to adapting their preferences and workflows—each trend influenced by ongoing advancements in platform capabilities, user guidance, and overall usability.

plu-ts

plu-ts is a library to enable Cardano-related software to be written entirely in TypeScript. It is not a new language either, but another eDSL closer to Plutarch conceptually than Aiken or Helios.

Scalus

Scala fans can use Scalus, which is a Scala implementation of Plutus. It is a set of libraries that works on both JVM and JavaScript. It was developed by Alexander Nemish, a former IOG engineer who worked on Marlowe previously. 


Andrew Westberg, NEWM CTO, speaking at the 2023 Dubai Cardano Summit


I think, for me, the way you get to a million users is by supporting many different languages and frameworks. So right now, Cardano kind of has this reputation of being all about Haskell and that's really not the case anymore. There's a whole lot of languages and frameworks that you can pick your own language that you want to build on, and there's the on-chain piece, and you can pick Haskell, you can pick Aiken, which is more of a Rust-like language... you can also work in Python, but most of the code for a dApp is actually off-chain... and for that, it's really important to know that you can pick whatever language that your team is good at, and that's that's really important for us to get to (that) millions and millions of developers.
Aiken to let you code
The language we have not mentioned yet, but will cover now, is Aiken which is the language with all the momentum in terms of developer adoption. It polled top spot among respondents to the State of the Cardano Developer Ecosystem 2023 survey question ‘What do you use (or plan to use) for writing Plutus script validators / smart contracts?’
 
Aiken, a newcomer, has made a remarkable entrance, garnering attention and use from developers across various experience levels. Its broad appeal underscores its emerging importance and sets the stage for whether it will sustain this positive impression in the times ahead.

So what's all the fuss about? Let's take a closer look…

Aiken was born from humble beginnings through the efforts of a small group of open source pioneers supported by TxPipe. The pool of contributors grew and the Cardano Foundation was quick to see its potential. The CF actively collaborates to advance Aiken with its core development team: Lucas Rosa, Kasey White and Matthias Benkort. The CF’s involvement aligns with its own mission to increase awareness of Cardano through operational resilience, education, and adoption.

Frederik Gregaard, CEO of Cardano Foundation


Aiken's story is a testament to how open-source initiatives can drastically reshape and improve existing infrastructures
Why Aiken? 

There are a few differences between ‘normal mainstream’ Haskell, running on your computer, and Haskell running on Cardano through the Plutus VM. The execution environments differ. To recap, the Cardano ledger only comprehends untyped Plutus core (UPLC), not Haskell. Haskell code must be compiled into Plutus core. When running on a computer, the compiled Haskell is translated into machine code for the machine’s hardware. On the Cardano blockchain, the Plutus VM executes the compiled Haskell, and the program behavior is slightly different.

For this reason the full ecosystem of functions and libraries available to ‘mainstream’ Haskell developers is not reusable on Cardano. Such libraries are important in any language, as they solve basic problems so are often required dependencies. When writing a program, these libraries are included at the top of your code, adding to the size of the program. 

Programming on Cardano is a different challenge, as space is at a premium. Only a subset of Haskell's wider ecosystem tooling can be leveraged on Cardano. It's important to emphasize this is not a Haskell-specific problem, it is a consideration when using any mainstream general purpose language for smart contracts. 
So in a sense, the Plutus platform is tied to Haskell’s existing language but with the addition of some libraries and program semantics which is not straightforward to work with. You can use whatever off-chain code you like with the Plutus platform, but it is heavily biased towards using Haskell on-chain and off-chain. Developers crave flexibility to use their favourite language for what is typically the largest part of their dApp, the off-chain component. 
So although Cardano is implemented in Haskell, including the node and the virtual machine that comes with it, it is UPLC that the Plutus VM actually executes. There is no dependency or reliance on Haskell. Other languages can compile to UPLC too. One of those is Aiken, which also has a version of this virtual machine written in Rust. Think of it as there being two implementations of the same virtual machine, with each acting as a UPLC interpreter in practice. 
Aiken origins

Aiken is named after Howard Aiken, the mathematician who invented the Harvard Mark I, the forerunner of the modern electronic digital computer. Aiken is a functional domain-specific language (DSL) with strong static typing and type inference. It is written in Rust and licensed under Apache-2.0. Unlike Haskell, it is built specifically with the Cardano blockchain in mind. It places an emphasis on the developer experience. It comes with ‘batteries included’ state-of-the-art tooling, taking inspiration from modern programming languages like Rust and Elm. Indeed, on the Aiken website, there is a credit to Louis Pilfold who created and maintains Gleam, the language from which a good chunk of Aiken was forked. 

Haskell has been around since the 90s, an old language, especially in crypto where it’s often said ‘crypto years are like dog years’. Its strengths are its battle-tested compiler and mature ecosystem. Some tools have aged poorly, however, laden with legacy features. As with most general-purpose languages, it comes with excess baggage that isn’t useful in a blockchain environment. Many developers struggle with Haskell and grow frustrated with the steep Plutus learning curve.

Aiken is a leaner language which aims to free itself from unnecessary features and instead provide a comprehensive opinionated solution with minimal configuration needed. Everything works out-of-the-box and with language-wide standards enforced by the compiler. Developers have remarked how Aiken is easy to learn and get started with in minutes. Under the covers, Aiken has a different execution model than the Haskell to Plutus Core compiler. While they both compile to UPLC, they represent and manipulate data slightly differently. This leads to different trade-offs regarding execution costs. This is important for later, when we review benchmark results from projects who have compared different options. 

Pi Lanningham (Sundae Labs CTO) -


When these languages started to pop up, I was really skeptical, because it takes a lot to write a programming language and to have like really high confidence that it produces correct code, because one small compiler bug and... you know we saw this on Ethereum ...there was a compiler bug that introduced reentrancy (vulnerability) and led to a bunch of hacks on a bunch of Dexes (decentralized exchanges) and so I was really skeptical of these new programming languages, because I was like 'oh you know I think it's really essential work, but it's going to take a very long time before they have kind of the confidence to be able to launch really big protocols like Sundaeswap on them'.... 


So on a whim one weekend I was like 'what would Sundaeswap’s contracts look like implemented in Aiken?' and let me tell you the speed at which I got a working prototype up was phenomenal....and the main reasons for that are: 1)  the language for me at least is a lot easier to read, so I was able to iterate a lot faster. 2) It has incredible tooling, so this is one of the things that Haskell is really known for is, it has really bad tooling, so even just to start a project it's like three or four days to install all the right dependencies, and get your environment set up to just compile a set of basic smart contracts... and then there's a lot of boilerplate that you don't really understand what it's doing if you're new to Smart contracts ...and so that adds like several other days before you even get your 'hello world' example right 


...with Aiken it's like 20 minutes and that's just because they've focused really heavily on the tooling for installing Aiken the first time for running and compiling smart contracts ...it's you know a breeze and it's super fast, you get really great error messages so this is a great example of that, you know if you're a developer this will mean something to you, if you're not don't worry about it and their tooling is very kind of smart contract-first



Figure 7.2: Aiken compiles to UPLC 
Although Aiken has familiar Rust-like syntax and a Rust compiler, it is not Rust. 

Matthias Benkort, @KtorZ:


The fun thing is, if you take Haskell and remove all the features that aren't useable on-chain and you add curly braces, you have Aiken. Aiken and Haskell have actually many similarities. More than Aiken and Rust in fact. So learning Aiken is even a good first step towards learning Haskell


Figure 7.3: Aiken syntax 

The Aiken team’s thoughtful design means the package manager encourages others to publish open source libraries. The language’s Rust libraries can be re-used for lower-level tools and services. Lucid is a good example of a service who have benefitted from this collaborative approach. Lucid is a library for creating Cardano transactions and off-chain code for Plutus contracts in JavaScript, Deno and Node.js. It leverages Aiken's UPLC crate to assess transactions before they’re submitted to calculate redeemer ExUnits. It does without using a node, Ogmios, or Blockfrost. The Lucid project now goes by Lucid Evolution and is maintained by Anastasia Labs. 

Aiken adopts a ‘keep it simple’ approach. Compared to other languages, Aiken scripts, by design, do not support as many features as general purpose Turing-complete languages. For example, there is no support for higher-kinded types or type classes. That's not to say they won’t be introduced at a later stage. 

Aiken is a small language, designed meticulously to produce concise, efficient scripts for on-chain Cardano smart contracts that integrate with most languages off-chain. ‘Aiken users exhibit a tendency for Rust in off-chain scenarios’ according to the findings of the State of the Cardano Developer Ecosystem 2023 survey. Hardly surprising considering how fast Rust is growing.

Aiken enables a smoother transition for developers new to Cardano, especially those used to programming in imperative languages. The interactive Aiken playground makes learning and experimenting with the language accessible. Developers can write, test, and debug Aiken code snippets in their browser. As outlined earlier, understanding the nuances and intricacies of the extended eUTxO model is a prerequisite to code effectively in Aiken. Through CIP-0057, Aiken supports blueprint stub generation. The stubs are effectively templates for different programming languages, facilitating an effortless integration between Aiken and off-chain components.

When it's time to build your on-chain contract, just type:



aiken build

The compiler generates a CIP-0057 Plutus blueprint and outputs it as plutus.json in your project's root directory. This blueprint describes the on-chain contract you just created. The resulting plutus.json file contains the compiled bytes of your smart contract, details about how to construct the types needed for your datum and redeemer. It's similar to an OpenAPI specification for your smart contract. This can then be used by code generation tools in your chosen language you use for off-chain components. Typescript, Javascript and Rust are the preferred languages for off-chain code according to the State of the Cardano Developer Ecosystem 2024 survey. Mesh.js and Blaze are just two popular off-chain frameworks, but there more and more options such as Elm Cardano which ‘aims to be the friendliest and most productive way of handling an off chain Cardano frontend’. 

Although Aiken may be more user friendly, it is still a pure functional programming language just like Haskell and maintains all the benefits of first-class functions, custom types, reusable, type-safe code, etc. You sometimes hear that Aiken offers everything a modern programming language should. But what does that actually mean?

Minimal setup is required, so developers don’t need to spend much time configuring their environment. Aiken offers a unified development experience, simple efficient process with little context-switching overhead. Error messages are friendly and helpful. Aiken’s Language Server Protocol (LSP) comes with auto-formatting, code completion, syntax-highlighting and integration with popular code editors. Creating documentation is no longer a chore as it can be generated from your code comments. Just add an extra slash to your comments, ///.


As you would expect with a functional programming language, there is an in-built unit testing framework. Leveraging the Plutus VMs deterministic nature, Aiken tooling allows for precise cost estimates, so smart contracts can be optimized to consume minimal resources. 


When you type 'aiken check', it runs the unit tests for you. In Cardano, there is this notion of an execution budget which you can think of as a guardrail to protect you from yourself. For example, if you inadvertently code up an infinite loop, it won’t do any damage because then it consumes the execution budget and stops the program. This is another feature leveraging the determinism that comes with the eUTxO model. 


Like unit-testing, property-based testing is also a breeze with Aiken. The testing framework is built in with Aiken…what does that mean? It means we can just write tests in our code, and check them immediately. Running aiken check returns true, or false along with a useful report detailing the memory and CPU execution units required for each test. This allows us to use tests to benchmark different versions of our code but grants flexibility also, as there’s no real execution limit as there is on-chain. 

Figure 7.4: Aiken test report
Projects using Aiken
Many Cardano projects have blogged about their benchmarking and comparison tests. We’ll chart some of their findings next. 
Indigo Protocol is a powerful dApp which brings real-world assets on-chain. It’s also a platform that offers decentralized synthetics trading on Cardano. Users can use Indigo to create synthetic assets called iAssets. A synthetic asset is a tokenized derivative that mimics the value of another asset. Synthetic assets give users exposure to a variety of assets without the need to own the underlying asset. This could be gold, silver or traditional stocks. 
Indigo’s smart contracts are some of the most complex within the Cardano ecosystem. As their protocol grew in popularity and usage, they needed to optimize. The Indigo Protocol transitioned from PlutusTx (enhanced with Plutonomy) to Aiken. 
Knowing the drawbacks of the PlutusTx language, Indigo Labs explored using Plutarch, plu-ts, Opsin and Helios before they decided on Aiken. After integrating Aiken, their performance metrics showed drastic improvements especially in terms of computational steps and memory units. Their blog details the arresting results of their competitive analysis of three phases in their development cycle:


PlutusTx: The foundational first layer.
PlutusTx with Plutonomy: The V1 contracts that were launched on Cardano mainnet. This was PlutusTx but optimized with Plutonomy, an optimizer for untyped plutus core..
Aiken: They state they chose Aiken for its ease of implementation, readability, and superior performance metrics.
They conclude that their ‘shift to Aiken is not just a technical upgrade — it’s a leap towards a more efficient and expansive future for both Indigo and the broader Cardano dApp ecosystem’.

Lenfi (formerly Aada Finance) is a decentralized liquidity protocol built on Cardano. The platform leverages the eUTxO model to enable peer-to-pool mechanics by introducing an innovative paradigm in DeFi lending. Lenfi was the first Cardano lending protocol written in Aiken. Their V1 rework was open-sourced in March 2023. They acknowledged the merits of Aiken as a viable alternative to Plutus-Tx for familiar reasons, reporting it gave them unparalleled efficiency and ease of use. For example, they used ‘Multi Validators’ which allows a spending validator and minting validator to share the same script hash.

JPG Store is the largest NFT marketplace on Cardano and the beating heart of its NFT culture. JPG Store has delivered several innovations including smart contracts, creator royalties and low fees. One of the differentiators for JPG Store is its commitment to supporting artists. The marketplace offers a fair and transparent fee structure, ensuring artists receive a significant chunk of the sales proceeds. This is the focus of CIP 27 - CNFT Community Royalties Standard. 

JPG Store has undergone several smart contract upgrades, each coming with improvements to the user experience. The latest upgrade to Jpg Store v3 saw smart contracts rewritten in Aiken and resulted in significant performance improvements, such as the ability to buy up to 50 NFTs in one transaction.


Aiken was the perfect fit for our needs. Setting up development environments was super simple in comparison to the complex requirements of a Plutus environment. Aiken also comes with a full testing suite and the syntax is much more approachable for the average developer than the Haskell-based syntax of Plutus.

MinSwap is a community-centric DEX available in more than 30 languages. A winning proposal from Catalyst Fund5, MinSwap is 100% community-funded. It is the dominant DEX in terms of TVL according to stats from Defi Llama and is the most-used dApp in the Cardano DeFi ecosystem. MinSwap V2 was written in Aiken smart contracts and its audit was funded by Catalyst and conducted by Sundae Labs. The Dex claims trading speeds improved by 5x and that ‘Minswap V2 isn't just an upgrade; it's a leap into a brighter, bolder Cardano DeFi future.’

SundaeSwap is another DEX making the move to Aiken smart contracts. They laid out the reasons in their Catalyst Fund10 proposal which was funded. They transitioned from ‘closed-source, inefficient’ PlutusTx contracts to Aiken providing a practical Aiken adoption case study while sharing learnings with the community. Those are just words, but the numbers don’t lie. In a demo on Cardano with Paul, Pi Lanningham revealed his benchmarking testing saw SundaeSwap smart contracts written in Aiken outperform their Plutus V1 counterpart by a significant margin. While Plutus filled just 164 orders, Aiken-powered smart contracts filled a remarkable 2258 orders. 

The on-chain Plutus code consumed more CPU resources, for 2–4 orders per batch. Aiken’s on-chain code was leaner, and resulted in 25 orders per batch. The benchmarking results concluded that under optimal conditions, a DEX utilizing Aiken could process approx 100 orders in just 4 batches, while a DEX built with Plutus could only manage 8–16 orders in the same timeframe. 

Sundae has also contributed several reusable Aiken libraries called Aicone and we are sure to hear more about their move to Aiken in the coming months. 

This was merely an orderve, there are many more projects using Aiken. Encoins, the first privacy-oriented protocol on Cardano, are using Aiken. There’s also Book.io, NEWM.io…not forgetting Hydra and Marlowe who have begun experimenting with Aiken, Charles Hoskinson revealed in an AMA

We're starting to fall in love with Aiken a little bit. The Hydra team actually prototyped some of the Hydra stuff with Aiken, and did a cross comparison to Plutus script and there's some good things there, it's great ecosystem

Fortuna is a Bitcoin style proof-of-work in smart contract form that showcases Aiken’s potential. Originally presented at a RareEvo workshop, it is a complete end-to-end example of a non-trivial smart contract which onboarded developers and became the 4th busiest Dapp within a week. It is open sourced with miners, explorers and tooling on GitHub. 

As we finally exit a long ‘crypto winter’, Aiken’s general availability release in September 2024 may be perfectly timed to attract a more diverse developer community to Cardano. The Awesome List of projects building with Aiken is sure to keep growing. As Lucas Rosa explained in a twitter space, the Aiken roadmap is mostly about improving tooling and formalizing parts of the Aiken compiler. 

Aiken has been indirectly audited by multiple in-depth security audits of dApps built with Aiken dApps. The feedback to date has been positive from the likes of Tweag.io and Sundae Labs looking into code generated by Aiken. It has also been indirectly tested through re-implementation of existing dApps that are themselves either formally verified (for example, Marlowe) or stress tested (for example, Hydra, SundaeSwap, etc...). So there is good confidence that the compiler is doing what it's meant to be doing.

The Aiken core development team talks regularly to the Plutus team, on issues like formalizing the Aiken compiler and leveraging the Haskell testing framework. Despite adopting a conservative approach of staying Alpha until September 2024, many projects were happily deploying Aiken in production, only after a rigorous battery of tests. It’s important to emphasize that Aiken and Haskell run on the same virtual machine in the Cardano ledger, both benefiting from the same security derived from that execution model.
Mars Attacks!

A smart contract, or validator, as they’re called in Aiken, guards a UTxO at that address. A user, or dApp, attempting to consume the UTxO must be ‘validated’ by meeting the conditions coded in the script. Leaving something ‘unguarded’, that ‘always succeeds’ can have dire consequences. This issue was highlighted in a high profile DDOS attack on Cardano in 2024.

The blockchain gods proved they have a sense of humour when the attacker sabotaged himself, however. Between June 24-25th 2024, an adversary executed the DDOS attack from three wallets, flooding the network with transactions containing scripts in an attempt to exhaust the network’s resources. 

The DDoS attack resulted in a high load on the network. Stake Pool Operators (SPOs) were negatively affected by the higher number of height battles. Despite these issues, the Cardano blockchain continued to operate effectively, with only minor delays in transaction processing times.

The eUTxO.org explorer captured the attack visually, with the grey gear icons representing the spam transactions that the attacker flooded the network with.  



The attack was halted after Philip DiSarro from Anastasia Labs posted instructions on X about how to take ada from the attacker. In short, when registering a staking script, a 2 ada deposit is required by the protocol and to reclaim this deposit back, you must deregister the script. 

The attacker was complacent as no validations were guarding the 194 scripts used in the attack, so there were no restrictions on who could reclaim deposits. As each validator was written to ‘always succeed’, and as the transaction fee was lower than the deposit obtained, the community confiscated the adversary's ada and the attack ended. 
General Availability
Aiken announced their Aiken General Release on X (twitter) in September 2024. The post featured a time lapse showing Aiken’s momentum over July, August and September, when it powered 52%, 55% and 63% of the smart contract traffic, respectively, on Cardano mainnet. 

The alpha release brought syntax changes, but a lot of improvements underneath the hood fine-tuning the compiler and enhanced tooling. The release coincided with the Chang hard fork which itself introduced new governance, built-in functions and cryptographic primitives enabling zero-knowledge capabilities. 

Plutus V3 incorporated changes outlined in CIP-0069 which affect the way the ledger and validators talk to each other. For Aiken, this meant it was easier to write multi-purpose validators in the same script. For example, a validator can contain multiple handlers each for one of six ‘purposes’, neatly summed up in this table from Aiken-lang.org.



Figure 7.5: Aiken handler ‘purposes’

CIP-0069 enabled a simplified developer experience when coding multi-validators. The new syntax is more readable and concise making life easier for audits. 





Figure 7.6: Aiken handler syntax


New approaches to ‘Conditional modules’ allow developers to use validator parameters as they see fit.  

Like most other languages, operators like && and || are right-associative so they don't bother with their second operand if the answer is in the first one. As everything is an expression, or predicate returning a Bool, this often leads to long chains of logical operators when coding more complex validators, eg. 


True && False && True || False
As these boolean checks are so ubiquitous in Aiken validators, you can now use more user-friendly keywords in place of logical operators, boosting readability further.

and {
 True,
 False,
 or {
   True,
   False,
 }
}


More technical features included ‘Backpassing’ which elegantly avoids heavily nested code full of callbacks. 

Easy documentation and error-handling continues to be a focus. Convenience and efficiency is standard for Aiken, for example, the use of aliases are often used to make type annotations more readable. As a compiled validator (smart contract) can seem like a black box in terms of troubleshooting, Aiken has a seamless tracing feature enabled with a single inline keyword. 

Aiken’s Language Server Protocol (LSP) support was extended further with more new features like automatic quick fixes for common compiler error messaging, and useful pop-up tips on hover.



Figure 7.7: Aiken editor tips

The comprehensive blog post from KtorZ goes into greater detail about other features like Soft-casting, Supercharged constants, Type-alias preservation, Datatype reification, property-based testing, Dependencies pruning, regression testing and formalization of the Aiken Intermediary Representation (AIR). There is also a nod to the Plutus team:


It is worth noting that some of those improvements are shared victories, as they also come from the brilliant work that the Plutus core team does on the base language of Cardano (a.k.a UPLC) and that we later harness within Aiken.


You can get started with Aiken in minutes with a simple install process. You can manage updates and versions with the companion command line called aikup. An upcoming Cardano Academy Aiken course will take you from ‘zero to hero’ and ready to tackle the Aiken video series on YouTube from  Rhys (STOIC Pool).

To keep updated follow @aiken_eng on twitter (X) and join the discord channel which is hosted in its original home, TxPipe’s discord server. TxPipe was the original home for Aiken, and Santiago Carmuega and his team continue to support the project. TxPipe are significant contributors to the ecosystem with products like Pallas and demeter.run. Pallas offers Rust-native building blocks for Cardano, which are used by Aiken internally for some features. demeter.run is similar to a cloud service that specializes in offering infrastructure and streamlined access to almost everything running on Cardano, including an Aiken starter kit. The CF recognises the important contribution TxPipe makes to Cardano and commits to supporting them in fostering adoption and growth.

Meanwhile Aiken continues to attract new fans and compliments. 

Aiken is incredible really. Plutus on rocket fuel - Algorand CTO, John Woods. 

The inaugural Cardano Buidler Fest drew an enthusiastic crowd in Toulouse in 2024 and the 2025 renewal in Vietnam is in the works. The Aiken community continues to grow, with more than 200 developers contributing to one of the Aiken core repositories. 

As a closing thought, consider a recent paper, ‘Smart Contract Languages: a comparative analysis’, where the researchers ask…
An open question is whether it is possible to reconcile the procedural style with the UTXO-based model, so to program smart contracts à la Solidity while preserving the key strengths of UTxO blockchains like Cardano (e.g., the absence of transaction-ordering dependencies and the parallelizability of transactions).
While it is perhaps too early to say definitively if Aiken has achieved this just yet, it has made great strides in a short space of time and with Zero Knowledge logic recently enabled, the future looks bright for developing on Cardano.




[^01]: Untyped Plutus Core, aiken-lang.org/uplc
[^02]: Helios compiler, github.com/Hyperion-BT/Helios/blob/main/helios.js
[^03]: Helios, hyperion-bt.org/helios-playground/
[^04]: Cardano smart contracts in Python, github.com/ImperatorLang/eopsin
[^05]: UPLC, github.com/OpShin/uplc
[^06]: Pluton, github.com/OpShin/pluthon
[^07]: We're Bringing Pure Python Development to Algorand, youtube.com/watch?v=94Re6nnUaQo
[^08]: Plutarch, github.com/Plutonomicon/plutarch
[^09]: Template Haskell, wiki.haskell.org/Template_Haskell
[^10]: @ravanave, twitter.com/ravanave/status/1736128883857015141
[^11]: State of the Cardano Developer Ecosystem - 2023, cardano-foundation.github.io/state-of-the-developer-ecosystem/2023/
[^12]: plu-ts, github.com/HarmonicLabs/plu-ts
[^13]: Scalus, github.com/nau/scalus
[^14]: Building dApps from Tools and Testing to Business Plans, youtu.be/CtQa2Rr448I?si=JSVVuWwgqeBSQOnv&t=151
[^15]: State of the Cardano Developer Ecosystem - 2023, cardano-foundation.github.io/state-of-the-developer-ecosystem/2023/#what-do-you-use-or-plan-to-use-for-writing-plutus-script-validators-smart-contracts
[^16]: TxPipe, txpipe.io/
[^17]: Aiken contributors, github.com/aiken-lang/aiken/graphs/contributors
[^18]: Lucas Rosa, github.com/rvcas
[^19]: Kasey White, github.com/MicroProofs
[^20]: Matthias Benkort, github.com/KtorZ
[^21]: AIKEN: A Game-Changer in the Cardano Landscape, linkedin.com/posts/gregaard_disrupting-defi-how-aiken-changed-the-cardano-activity-7110592762621648896-l070
[^22]: Aiken VM written in Rust, github.com/aiken-lang/aiken/blob/main/crates/uplc/src/machine.rs#L63
[^23]: Type inference refers to the automatic detection of the type of an expression in a formal language.
[^24]: Aiken credits, aiken-lang.org/credits
[^25]: Gleam, gleam.run/
[^26]: Cardano Foundation Developer Survey 2022, cardano-foundation.github.io/state-of-the-developer-ecosystem/2022/#how-satisfied-are-you-with-the-current-state-of-the-plutus-ecosystem
[^27]: The term Opinionated software solutions relates to the level of guidance and structure a software solution provides. An opinionated solution usually comes with a predefined set of conventions, best practices and design patterns. It shephards developers in a certain direction, which can speed up development but can sometimes limit flexibility.
[^28]: Aiken Brings a Massive Cardano Smart Contract Performance Increase, youtu.be/4Y1UieAhszY?si=0CwhInAT2sR4mNXd&t=626
[^29]: A reentrancy attack occurs when a function is externally called during its execution, enabling it to be run several times in a single transaction. This usually occurs when a smart contract calls another smart contract before it resolves its state.
[^30]: A package manager provideS a method to install new dependencies (packages), manage where packages are stored on your file system, and enables you to publish your own packages.
[^31]: Lucid, lucid.spacebudz.io/
[^32]: Aiken UPLC crate, crates.io/crates/uplc
[^33]: A crate is the smallest amount of code that the Rust compiler considers at a time
[^34]: Ogmios is a lightweight bridge interface for cardano-node
[^35]: Blockfrost is an API-as-a-service that allows users to interact with Cardano and other parts of its ecosystem
[^36]: A higher-kinded type is a type that allows you to create generic structures that can work with a wide range of data types
[^37]: A type class is a type system construct that supports ad hoc polymorphism
[^38]: State of the Cardano Developer Ecosystem - 2023 survey, cardano-foundation.github.io/state-of-the-developer-ecosystem/2023/
[^39]: Rust is growing, flawless.dev/essays/rust-is-growing/
[^40]: Aiken Playground, play.aiken-lang.org/
[^41]: Plutus Contract Blueprint, cips.cardano.org/cip/CIP-0057
[^42]: CIP-0057? | Plutus Smart-Contract Blueprints, github.com/cardano-foundation/CIPs/pull/258
[^43]: Optimizing the Throughput of Cardano: The Evolution of Indigo Protocol’s Smart Contracts, indigoprotocol1.medium.com/optimizing-the-throughput-of-cardano-the-evolution-of-indigo-protocols-smart-contracts-a498ecc42823
[^44]: Lenfi V1, github.com/aadafinance/aada_v1_aiken
[^45]: CNFT Community Royalties Standard, cips.cardano.org/cip/CIP-0027
[^46]: Jpg store v3, medium.com/@jpgstorenft/unveiling-the-next-gen-smart-contract-update-for-jpg-store-2f883c913979
[^47]: MinSwap Aiken v2 Audit, lidonation.com/sw/proposals/minswap-aiken-v2-audit-f10
[^48]: SundaeSwap Aiken proposal, lidonation.com/sw/proposals/sundaeswap-aiken-smart-contracts-f10
[^49]: Aiken Brings a Massive Cardano Smart Contract Performance Increase, youtu.be/4Y1UieAhszY?si=0CwhInAT2sR4mNXd
[^50]: Aicon libraries, github.com/SundaeSwap-finance/aicone
[^51]: Surprise AMA October 8th, 2023, youtube.com/live/Bvedd--CoPw?si=7SM0TTPmYpxMXfjH&t=158
[^52]: Fortuna, github.com/aiken-lang/fortuna?tab=readme-ov-file
[^53]: Awesome Aiken, github.com/aiken-lang/awesome-aiken#readme
[^54]: Bitrue x @Cardano_CF #AMA, twitter.com/i/spaces/1mnxeRpqDBEKX
[^55]: Aiken discord, discord.gg/Vc3x8N9nz2
[^56]: Simplifying Cardano dApp development with Demeter, cardanofoundation.org/en/news/simplifying-cardano-dapp-development-with-demeter/
[^57]: John Woods on Aiken, twitter.com/JohnAlanWoods/status/1706222469856608267?t=93aSQDQ9c6GKhRW73GWzHQ&s=19
[^58]: Cardano Builder Fest, buidl.2024.cardano.org
