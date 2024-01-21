# Chapter 7: Aiken ❤️

*‘I am a simple man and I want simple answers’* ― Howard Aiken

<br><br>
A much perpetuated myth is that you must learn Haskell to write smart contracts on Cardano. Let’s zoom out for a moment, to understand the bigger picture. Haskell programs, coded on the Plutus Platform, do indeed compile to Untyped Plutus Core (UPLC)[^01] and while the Cardano ledger only understands Plutus Core, this low-level machine language is not something developers code in day to day. So while you can use Haskell exclusively if you want, the reality is you can choose from a growing list of high-level languages which compile to UPLC. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig71.png "figure 7.1")
<br>**Figure 7.1:** Smart Contracts Programming on Cardano drawing by @_KtorZ_ 

That’s enough to give you context of the low-level intricacies, the rest of this chapter will focus on the top left of the drawing, the high-level languages available on Cardano. Most developers prefer these languages as they can express business logic easily with a rich vocabulary, and the code is generally more readable and optimized for audits and static analysis.

**Helios** is a Domain Specific Language (DSL) that compiles to Plutus-Core. It is a new language built from the ground up with Cardano in mind. Helios is also a functional language but is very similar to TypeScript. Notably, Helios’s compiler is just a single javascript file[^02] with no external dependencies to any library, so the Helios team has kept control of their ecosystem. The flip side is everything must be built from scratch, and this takes time for the language APIs, SDKs and tooling to mature. Helios is geared for building client applications in the browser[^03] but is also easy to use from within a javascript project.  

**OpShin**[^04] is an implementation of Cardano smart contracts written in a strict subset of normal Python. It enables you to write smart contracts in completely valid, albeit restricted Python3. OpShin implements its own type system and compile-time checks to ensure correctness. Python packages for UPLC[^05] and pluto[^06] have been made available for anyone that wants to build UPLC tooling in Python. 

Interestingly, Algorand[^07] has adopted a similar strategy that hinges on the benefit of using normal Python, which brings with it all the features that come with developing on Python such as widespread editor support, language servers, linters, testing frameworks and verification tools. 

**Plutarch**[^08] is a typed eDSL (embedded domain specific language) in Haskell for writing efficient Plutus Core validators. It is not a new language, it’s just good old Haskell with no restrictions. Some say Plutarch is the language PlutusTx could have been, with no Template Haskell[^09] involved. Axo,[^10] one of the most anticipated decentralized exchanges to launch on Cardano, was built with Plutarch. 

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/jarek.png "Axo tweet")

<br>From the 2023 Cardano Developer Ecosystem Survey[^11]

> Meanwhile, Plutarch appears to find its niche among more seasoned developers, suggesting its appeal might be rooted in advanced features or complexities that cater more effectively to those with extensive backgrounds. This dynamic illustrates a vibrant and responsive ecosystem, with innovative tools emerging and developers open to adapting their preferences and workflows—each trend influenced by ongoing advancements in platform capabilities, user guidance, and overall usability.

**plu-ts**

plu-ts[^12] is a library to enable Cardano-related software to be written entirely in TypeScript. It is not a new language either, but another eDSL closer to Plutarch conceptually than Aiken or Helios.

**Scalus**

Scala fans can use Scalus,[^13] which is a Scala implementation of Plutus. It is a set of libraries that works on both JVM and JavaScript. It was developed by Alexander Nemish, a former IOG engineer who worked on Marlowe previously. 

Andrew Westberg, NEWM CTO, speaking at the 2023 Dubai Cardano Summit[^14]

>I think, for me, the way you get to a million users is by supporting many different languages and frameworks. So right now, Cardano kind of has this reputation of being all about Haskell and that's really not the case anymore. There's a whole lot of languages and frameworks that you can pick your own language that you want to build on, and there's the on-chain piece, and you can pick Haskell, you can pick Aiken, which is more of a Rust-like language... you can also work in Python, but most of the code for a dApp is actually off-chain... and for that, it's really important to know that you can pick whatever language that your team is good at, and that's that's really important for us to get to (that) millions and millions of developers.

## Aiken is born

The language we have not mentioned yet, but will cover now, is Aiken which is the language with all the momentum in terms of developer adoption. It polled top spot among respondents to the *State of the Cardano Developer Ecosystem 2023* survey question[^15] ‘What do you use (or plan to use) for writing Plutus script validators / smart contracts?’
 
>‘Aiken, a newcomer, has made a remarkable entrance, garnering attention and use from developers across various experience levels. Its broad appeal underscores its emerging importance and sets the stage for whether it will sustain this positive impression in the times ahead.’

So what's all the fuss about? Let's take a closer look…

Aiken was born from humble beginnings through the efforts of a small group of open source pioneers supported by TxPipe.[^16] The pool of contributors[^17] grew and the Cardano Foundation was quick to see its potential. The CF actively collaborates to advance Aiken with its core development team: Lucas Rosa,[^18] Kasey White[^19] and Matthias Benkort.[^20] The CF’s involvement aligns with its own mission to increase awareness of Cardano through operational resilience, education, and adoption.

Frederik Gregaard, CEO of Cardano Foundation[^21]

>‘Aiken's story is a testament to how open-source initiatives can drastically reshape and improve existing infrastructures’

## Aiken fills the gaps

There are a few differences between ‘normal mainstream’ Haskell, running on your computer, and Haskell running on Cardano through the Plutus VM. The execution environments differ. To recap, the Cardano ledger only comprehends untyped Plutus core (UPLC), not Haskell. Haskell code must be compiled into Plutus core. When running on a computer, the compiled Haskell is translated into machine code for the machine’s hardware. On the Cardano blockchain, the Plutus VM executes the compiled Haskell, and the program behavior is slightly different.

For this reason the full ecosystem of functions and libraries available to ‘mainstream’ Haskell developers is not reusable on Cardano. Such libraries are important in any language, as they solve basic problems so are often required dependencies. When writing a program, these libraries are included at the top of your code, adding to the size of the program. 

Programming on Cardano is a different challenge, as space is at a premium. Only a subset of Haskell's wider ecosystem tooling can be leveraged on Cardano. It's important to emphasize this is not a Haskell-specific problem, it is a consideration when using any mainstream general purpose language for smart contracts. 
So in a sense, the Plutus platform is tied to Haskell’s existing language but with the addition of some libraries and program semantics which is not straightforward to work with. You can use whatever off-chain code you like with the Plutus platform, but it is heavily biased towards using Haskell on-chain and off-chain. Developers crave flexibility to use their favourite language for what is typically the largest part of their dApp, the off-chain component. 
So although Cardano is implemented in Haskell, including the node and the virtual machine that comes with it, it is UPLC that the Plutus VM actually executes. There is no dependency or reliance on Haskell. Other languages can compile to UPLC too. One of those is Aiken, which also has a version of this virtual machine[^22] written in Rust.

## What is Aiken?


**_The rest will be uploaded soon..._**

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
