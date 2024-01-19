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
[^22]:
