# Chapter 7: Aiken ❤️

*‘I am a simple man and I want simple answers’* ― Howard Aiken

<br><br>
A much perpetuated myth is that you must learn Haskell to write smart contracts on Cardano. Let’s zoom out for a moment, to understand the bigger picture. Haskell programs, coded on the Plutus Platform, do indeed compile to Untyped Plutus Core (UPLC) and while the Cardano ledger only understands Plutus Core, this low-level machine language is not something developers code in day to day. So while you can use Haskell exclusively if you want, the reality is you can choose from a growing list of high-level languages which compile to UPLC. 


Figure 7.1: Smart Contracts Programming on Cardano drawing by @_KtorZ_ 
That’s enough to give you context of the low-level intricacies, the rest of this chapter will focus on the top left of the drawing, the high-level languages available on Cardano. Most developers prefer these languages as they can express business logic easily with a rich vocabulary, and the code is generally more readable and optimized for audits and static analysis.

Helios is a Domain Specific Language (DSL) that compiles to Plutus-Core. It is a new language built from the ground up with Cardano in mind. Helios is also a functional language but is very similar to TypeScript. Notably, Helios’s compiler is just a single javascript file with no external dependencies to any library, so the Helios team has kept control of their ecosystem. The flip side is everything must be built from scratch, and this takes time for the language APIs, SDKs and tooling to mature. Helios is geared for building client applications in the browser but is also easy to use from within a javascript project.  

OpShin is an implementation of Cardano smart contracts written in a strict subset of normal Python. It enables you to write smart contracts in completely valid, albeit restricted Python3. OpShin implements its own type system and compile-time checks to ensure correctness. Python packages for UPLC and pluto have been made available for anyone that wants to build UPLC tooling in Python. 

Interestingly, Algorand has adopted a similar strategy that hinges on the benefit of using normal Python, which brings with it all the features that come with developing on Python such as widespread editor support, language servers, linters, testing frameworks and verification tools. 

Plutarch is a typed eDSL (embedded domain specific language) in Haskell for writing efficient Plutus Core validators. It is not a new language, it’s just good old Haskell with no restrictions. Some say Plutarch is the language PlutusTx could have been, with no Template Haskell involved. Axo, one of the most anticipated decentralized exchanges to launch on Cardano, was built with Plutarch. 



From the 2023 Cardano Developer Ecosystem Survey

Meanwhile, Plutarch appears to find its niche among more seasoned developers, suggesting its appeal might be rooted in advanced features or complexities that cater more effectively to those with extensive backgrounds. This dynamic illustrates a vibrant and responsive ecosystem, with innovative tools emerging and developers open to adapting their preferences and workflows—each trend influenced by ongoing advancements in platform capabilities, user guidance, and overall usability.

plu-ts

plu-ts is a library to enable Cardano-related software to be written entirely in TypeScript. It is not a new language either, but another eDSL closer to Plutarch conceptually than Aiken or Helios.

Scalus

Scala fans can use Scalus, which is a Scala implementation of Plutus. It is a set of libraries that works on both JVM and JavaScript. It was developed by Alexander Nemish, a former IOG engineer who worked on Marlowe previously. 


Andrew Westberg, NEWM CTO, speaking at the 2023 Dubai Cardano Summit


I think, for me, the way you get to a million users is by supporting many different languages and frameworks. So right now, Cardano kind of has this reputation of being all about Haskell and that's really not the case anymore. There's a whole lot of languages and frameworks that you can pick your own language that you want to build on, and there's the on-chain piece, and you can pick Haskell, you can pick Aiken, which is more of a Rust-like language... you can also work in Python, but most of the code for a dApp is actually off-chain... and for that, it's really important to know that you can pick whatever language that your team is good at, and that's that's really important for us to get to (that) millions and millions of developers.
Aiken is born


**_To be uploaded soon..._**
