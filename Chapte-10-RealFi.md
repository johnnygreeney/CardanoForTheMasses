# Chapter 10: RealFi on Cardano

*‘Wealth consists not in having great possessions, but in having few wants’* 
<br>― Epictetus

~~DeFi~~ RealFi for the Masses

Blockchain-agnostic sites like DefiLlama chart the consistent growth[^01] of Cardano’s TVL (total value locked), setting new highs regularly in spite of the current bear market slump. One only has to look at CardanoCube to see an expanding diverse ecosystem of projects. This is before we even have a mature USD-backed stablecoin. The growth of DeFi on Cardano is inevitable at this stage.

**August 30, 2020, DeFi ‘network effect’.** CH:[^02]

>The reality is that the first mover advantage is actually a disadvantage in DeFi. Those network effects were ephemeral and often covered with mistakes, scars and explosions. You actually want to be in the imitator, the second mover category for DeFi, and I think we’ll have a lot more luck than the first movers did in the space and there’ll be a mass exodus because those first mover architectures and designs are just too inflexible, and Cardano is much better suited as a platform.

What is perhaps more interesting to track the projects offering novel, real-world utility. The term *RealFi* was originally coined by IOG’s African operations director, John O’Connor, in his blog in 2021.[^03] The phenomenon that is DeFi (decentralized finance) is the focus of many outsiders looking at the crypto industry. Studies like the *SoK: Decentralized Finance*[^04] paper from the Imperial College London lay out the core concepts. 

RealFi is a superset of DeFi, proposing a regulatory framework made up of four additional features:

- identity, 
- metadata, 
- governance, 
- standards and certification 

**Identity** is the notion that a dApp itself would have some agency. It would have an ID, and its users would have IDs… not traditional IDs as we know them in Web 2,[^05] but perhaps decentralized IDs (DIDs) that would still allow them to prove know your customer (KYC) and abide by anti-money laundering (AML) laws, etc. A user can retain some anonymity yet still be able to selectively disclose data when necessary. 

**Metadata** is setting the context for transactions and actors in a system. It is the wider story of why a transfer took place, why certain data was or wasn’t provided. It can be the terms and conditions, the end user agreement, signed before using a DEX, etc. 

**Governance** is how the system is maintained. How does a decentralized community upgrade, update and change parameters in DeFi? Who, and by what means, implements change? What is the threshold for certain actions? Why is the threshold set differently for certain updates? Who decides what is a critical update? What mechanisms are in place? How automated should they be?

**Standards** and **certification** in RealFi are still emerging and to be agreed upon. These are the measures by which dApps and projects can be assessed in marketplaces. In a decentralized, open ecosystem, they can be optional but enable users to know more about a product or service provider.

These four features can be used to implement some form of regulatory structure that can be tailored for any jurisdiction. It is now inevitable regulation is coming to the crypto industry after the spate of debacles[^06] in 2022, the FTX trial and SEC crackdown on centralized exchanges in 2023. This framework goes some way to meeting the regulator halfway and forming decentralized regulation, aka dReg, aka ‘reg tech’. There needs to be some form of overlay for the standard regulatory measures such as transaction reversals, asset freezing, etc.

The motives behind DeFi have too often been ‘get rich quick’ schemes, with bad actors using customer funds to pay for celebrity adverts, or vanity naming rights for sports stadiums. 

There’s rarely any intention of offering real loans to people who need them in oppressed regions, without access to basic credit or monetary system. The reason it’s called RealFi is, beyond the fact that you have these four features above, you also have real use and adoption of an alternative to the traditional financial operating system. A blockchain-based, crypto-based financial stack built on protocols and egalitarianism, instead of centralized entities that repeatedly collapse due to human greed, incompetence, and corruption.

The rest of this chapter outlines some of the building blocks for RealFi. You’ll notice that nothing is controlled by a single government, or federated entity. 

**November 24, 2020. Re: motivation behind Cardano.** CH:[^07]

>So why does Cardano exist? I did a TED talk in 2014 and I have not deviated since I did it. I said I care about economic identity. Every day we wake up, there’s three billion people who don’t have economic identity. They’re unbanked, they’re outside of the global economy. They get screwed…they pay 85% interest on loans. When their kids go to London and work as maids and wire money back, there’s a 15% charge for that. When they get money, they can’t hold on to it. They have no insurance, so when a disaster happens, they’ve nothing to cover it with. So one bad event, one monsoon, one hurricane…they’re done. That’s the reality for three billion people.
>
> . . . So, what’s the solution? You can be a bleeding heart liberal and go around donating…telethons don’t work. You need an economic solution and the only way to have such a solution is to give people economic identity. You have to give them their own identity, banking system, insurance and lending systems. What are we doing? We are giving people stablecoins, exchanges, the ability to securitize their business interests, peer-to-peer lending, the ability to quantify knowledge with oracles, new business models like decentralized media, decentralized content sharing, new venture capital models… that is what our industry is about at its core.

## Decentralized IDs 

To define digital identity, we must first understand all that identity entails. A digital identity is data used by a computer to represent an external agent. This can be a person, organization, application, or device. A verifiable credential is a set of claims and metadata that cryptographically prove who issued it. They are similar to the physical documents you use like a driver’s license or passport.

A digital entity might use a verifiable credential to share information online. This exchange of info poses some concerns about security, however, like how safe is the data you share once it’s out there in the open. Who really controls the data? Is it really decentralized? 

With social media requesting so much personal information, and centralized crypto exchanges behaving like banks, securing your own identity has never been more important. **Self-Sovereign Identity** (SSI) and decentralized IDs (DIDs) aim to solve this problem. 

Self-sovereign identity is an approach to digital identity, based on a set of principles,[^08] that gives individuals control over the information they use to prove who they are online. 

Decentralized identifiers (DIDs) are a type of identifier that allows for verifiable, decentralized digital identity. A DID can be tied to any subject (e.g., a person, organization, thing, data model, abstract entity, etc.) as determined by the controller of the DID. The World Wide Web Consortium (W3C) DID Working Group defines a DID in its core specification:

- DIDs are controlled by the entities that hold them,
- They enable cryptographic authentication of the DID holder,
- They describe the discovery of information needed to launch secure and privacy-preserving communication methods.
- Give access to service-independent data portability.

In June 2022, the World Wide Web Consortium (W3C) approved the advancement of the DID core specification to the W3C *Recommendation* stage. This was a milestone as it endorsed the continuous research of digital identity, and paves the way for identity platforms such as Atala PRISM and the Cardano Foundation’s Identity Wallet.[^09] The approval of the specification, opposed by some big tech giants (Google, Apple, et al), gives the DIDs credibility and impetus for broader adoption. 

**Atala PRISM** is a digital identity platform built on SSI (self-sovereign identity) core principles. It is IOG’s suite of services for verifiable data and digital identity. The Atala Prism team have been working with DIDs for some time. They have implemented large scale solutions such as the partnership with the Ethiopian Ministry of Education to track students’ progress. 

Atala Prism V2 built on the lessons of the past few years, and addresses issues like conforming to standards and compliance with laws such as the Travel Rule.[^10] It is now an Open Enterprise Agent with an open source code base in Hyperledger Labs. It is also built for seamless integrations with IOGs’ *Lace*
light wallet. 

Open source is all about giving users options. The Cardano Foundation targets enterprise businesses and organizations. They focus more on building tools in Java, as it remains the predominant language for enterprise developers. In 2023, the CF created Ledger Sync and the **Identity Wallet** in Java to drive enterprise adoption. The CF’s new W3C-compatible mobile wallet manages self-sovereign identities across Cardano and other blockchain networks. 

The wallet will securely generate, update, deactivate, and restore Decentralized Identifiers (DIDs) and KERI (Key Event Receipt Infrastructure)[^11] Autonomic Identifiers (AIDs). The strategy is to '*establish trusted connections with DIDComm for communications and W3C verifiable credentials and Authentic Chained Data Containers (ACDCs)*'.

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig101.png "figure 10.1")
<br>**Figure 10.1:** The benefits of SSI and the Cardano Foundation Identity Wallet 

## Babel Fees



**_To be uploaded soon..._**



[^01]: Cardano Enters Top 10 by TVL, medium.com/tap-in-with-taptools/cardano-enters-top-10-by-tvl-e9fd873ee064
[^02]: Surprise AMA 08302020, youtu.be/lIz3GnCHbOc?t=993
[^03]: Welcome to the age of RealFi, iohk.io/en/blog/posts/2021/11/25/welcome-to-the-age-of-realfi
[^04]: SoK: Decentralized Finance (DeFi), berkeley-defi.github.io/assets/material/defi-sok-ariah-2101.08778.pdf
[^05]: Web 2.0 allows anyone to create content but centralizes authorities and gatekeepers, such as major search engines and social media platforms. Web3 enables peer-to-peer interactions without centralized platforms and intermediaries.
[^06]: Top 10 Crypto Scams and Hacks of 2022, u.today/top-10-crypto-scams-and-hacks-of-2022
[^07]: CROW..Live With Charles Hoskinson of Cardano ADA 11/24/20, youtube.com/watch?v=z3s6olBfbfA
[^08]: SSI principles, github.com/WebOfTrustInfo/self-sovereign-identity/blob/master/self-sovereign-identity-principles.md
[^09]: CF digital identity wallet, identity.cardanofoundation.org/
[^10]: The Travel Rule requires parties to obtain and exchange beneficiary and originator information with virtual assets transfers over a certain threshold. 
[^11]: Key Event Receipt Infrastructure (KERI) has a decentralized secure root-of-trust based on cryptographic self-certifying identifiers. It uses hash chained data structures called Key Event Logs that enable ambient cryptographic verifiability. Any log may be verified anywhere at anytime by anybody
[^12]: Babel Fish, hitchhikers.fandom.com/wiki/Babel_Fish
[^13]: Babel Fees, iohk.io/en/blog/posts/2021/02/25/babel-fees/
[^14]: Cardano360 - February 2021, youtu.be/YXaK0cvgoFQ?t=2184
[^15]: Chakravarty, Karayannidis, Kiayias, Peyton Jones, Vinogradova (2022), 'Babel Fees via Limited Liabilities', iohk.io/en/research/library/papers/babel-fees-via-limited-liabilities/
[^16]: HODL is slang in the cryptocurrency community for holding the cryptocurrency rather than selling it. HODL can also mean ‘Hold On for Dear Life’ and refers to not selling, even during strong market volatility and poor market performance.
[^17]: Game theory is the study of mathematical models of strategic interaction in between rational decision-makers. It has applications in all fields of social science, as well as in logic and computer science. Originally, it addressed zero-sum games, in which each participant’s gains or losses are exactly balanced by those of the other participants. Today, game theory applies to a wide range of behavioral relations and is now an umbrella term for the science of logical decision making in humans, animals, and computers.
[^18]: Roundtable with Charles Hoskinson and Alex Chepurnoy | Ergo Pulse, youtube.com/watch?v=k9a3SYV6FJA
[^19]: **Spot trading** is a continuous process of buying and selling tokens and coins at a spot price for immediate settlement. The trader usually intends to gain profits from market fluctuations
[^20]: An **atomic swap** is an exchange of cryptocurrencies from separate blockchains. The swap is conducted between two entities without a third party's involvement. The idea is to remove centralized intermediaries like regulated exchanges and give token owners total control
[^21]: Babel fees via limited liabilities, youtube.com/watch?v=iJEmRZ6leXE
[^22]: Surprise AMA 02/26/2021, youtu.be/6eD_rnII3ms?t=42
[^23]: **Tether** (ticker USDT) is a cryptocurrency that is hosted on the Ethereum and Bitcoin blockchains, among others. Its tokens are issued by the Hong Kong company Tether Limited, which in turn is controlled by the owners of Bitfinex. Tether is called a stablecoin because it was originally designed to always be worth US$1.00, maintaining $1.00 in reserves for each tether issued.
[^24]:
[^25]:
[^26]:
[^27]:
[^28]:
[^29]:
[^30]:
[^31]:
[^32]:
[^33]:
[^34]:
[^35]:
[^36]:
[^37]:
[^38]:
[^39]:
[^40]:
[^41]:
[^42]:
[^43]:
[^44]:
[^45]:
[^46]:
[^47]:
[^48]:
[^49]:
[^50]:
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
