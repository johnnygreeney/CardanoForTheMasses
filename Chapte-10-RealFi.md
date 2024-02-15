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

Cardano is introducing a novel mechanism that allows the payment of transaction fees in user-defined tokens on Cardano. Babel fees are named after the Babel fish,[^12] a creature in Douglas Adam’s book **The Hitchhiker’s Guide to the Galaxy** that enables you to hear any language translated into your own. Despite the galaxy’s many varied languages, this vision of global translation provides for meaningful communication.

Smart contracts allow for the creation of a wide range of unique tokens in the cryptocurrency sector. Babel fees are based on the idea of using your preferred token to interact with the platform. Similar to how you would interact with legacy financial systems, where you would use your local currency by just making a selection in a dropdown. ‘Babel fees’ convert the token you’re using to the one required by the platform for transactions or whatever trade you want to execute on the platform. IOG’s chief scientist, Prof Aggelos Kiavias,[^13] was ahead of the curve when introducing this concept early in 2021. IOG also produced a video whiteboard walkthrough on their ‘IOHK’ YouTube channel at the time. The paper ‘Babel Fees via Limited Liabilities’ was subsequently published in April 2022.[^14]

In most blockchains, it’s typical that a legitimate transaction must come at a cost to the sender. Without such a limitation, anybody may overwhelm the system with minor transactions, overflowing its capacity and leaving it worthless. On that basis, a common implication is that for any blockchain that supports user-defined currencies, paying transaction fees in such tokens should be forbidden. Instead, transactions should be charged a fee in the platform’s native token, which is seen as valuable by all the token holders (hodlers).[^15] It’s arguable that such a limitation is bad for adoption and interoperability with other blockchains and legacy systems. How are IOG planning to work around this shortcoming?

**eUTXO enables innovation** 

Cryptography and game theory[^16] have a history of making the seemingly impossible achievable. Cardano’s Extended UTXO (eUTXO) architecture enables a solution because of how native assets function on the platform. 

Tokens may be generated using a minting policy, and they are regarded similarly to ada on the ledger. Creating a valid transaction requires the consumption of one or more UTXOs. On Cardano, a UTXO may hold more than simply ada; it can also handle a token bundle containing numerous distinct tokens, both fungible and non-fungible. It is therefore feasible to use a single UTXO to construct transactions that transfer many distinct tokens. Ergo, underrated pioneers in the crypto space, have already delivered 15k outputs per transaction using EUTXO and rollups.[^17] 

The ledger’s transaction fees are priced in ada, using a function fixed as a ledger parameter. The costs necessary for a successful transaction may be anticipated accurately prior to execution, which is a key strength of Cardano’s EUTXO architecture. This is a unique property that other ledger configurations do not have. 

**How will Babel Fees work?**

Babel fees enable a transaction to announce an ada-denominated debt equal to the amount of fees the transaction issuer is required to pay. A transaction like this would be rejected by the ledger. However, it might be seen as an open offer in which the debt is taken on. Why would someone accept such a burden? To make this attractive, the transaction may give some quantity of token(s) to whoever covers the debt. The assumption being the token bundle is already existing in Cardano. This would be a one-to-one transaction between ada and the given token(s) at a fixed rate. 

Consider a block producer who notices a transaction like this. The block producer may generate a matching transaction and claim the tokens on offer by absorbing the debt and covering it with ada. The transaction with the debt, as well as its matching transaction, become admissible to the ledger as a group. The set of two transactions becomes priced in ada as a whole because of the debt absorption, and so it does not violate the ledgers’ accounting requirements in terms of ada fees. Therefore, the transaction with the debt is settled. 

Users can propose transactions priced in whatever token(s) they own and have them settle in the ledger as normal transactions if a block maker is ready to take them up on the spot trade.[^18] This shows how native assets, the EUTXO architecture, and the small but powerful change of adding liabilities in the form of negative values in token bundles can handle Babel fees, allowing users to price transactions in any token that the system supports natively.

For the above concept to work, Cardano must have liquidity providers who have ada and are ready to issue matching transactions. The ecosystem of thousands of stake pool operators (SPOs) are obvious initial candidates to make the market by advertising exchange rates for their preferred tokens, etc.

Following the introduction of native assets with the *Mary* hard fork, the possibility of negative amounts in token bundles can be incorporated into Cardano’s ledger rules. Aside from Babel fees, this opens up other use cases such as atomic swaps[^19] for spot transactions. It’s just another example of how Cardano innovates instead of forking and copying first and second-generation blockchains.

**A worked example**

Below is an example transaction in human readable format. This is about Bill, Ted and Barney exchanging ada and a new native token, JohnCoin (JCN). 

**Transaction**:
< Receive 20 ada from Bill
> Send 10 ada to Ted
> Send 9.66 ada to Bill
–Use 0.34 ada as the transaction fee

Bill has received 20 ada in the past, so has a UTXO worth 20 ada in Daedalus. He takes that UTXO, sends 10 ada to Ted, 9.66 ada back to himself, and uses the leftover 0.34 as the transaction fee. For it to be a legitimate transaction, the inputs and the outputs must be equal, ie.  20 = 10 + 9.66 + 0.34


Now let’s look at a transaction that uses JohnCoin, JCN as well as ada.

**Transaction**:
<Receive 20 JCN from Bill
<Receive 4 ada from Bill
>Send 10 JCN to Ted
>Send 10 JCN to Bill
>Send 3.66 ada to Bill
–Use 0.34 ada as the transaction fee

This time Bill wanted to send 10 JCN to Ted. He also had to include some ‘extra’ ada to cover the transaction fee. It worked fine, but it was inconvenient and not really sustainable if we were dealing with hundreds, or thousands, of transactions. 

Here’s how this same transaction would work with Babel fees.

**Transaction**:
<Receive 20 JCN from Bill
>Send 10 JCN to Ted
>Send 8 JCN to Bill
>Send -0.34 ada and 2 JCN to whomever takes on the debt
–Use 0.34 ada as the transaction fee

This poses some questions:

How can Bill pay the 0.34 ada fee if he didn’t have any ada in Daedalus begin with? With babel fees, this isn’t a problem. So long as the inputs equal the outputs, the transaction is legit. The negative and positive ada in the outputs cancel each other out.

How can Bill send a negative amount of ada to just anyone, as a valid transaction? It isn’t a valid transaction until someone ‘volunteers’ to take on the debt. It has to be voluntary as no one can be sent negative ada without their permission. Why would anyone ‘volunteer’ to take on the debt? They would not only take on the debt, ie. the negative ada, they would also receive the additional 2 JCN.

So the first user to ‘volunteer’ to take on the debt, Barney in this example, will make a transaction as follows:

Transaction:
<Receive 4 ada from Barney
<Receive -0.34 ada and 2 JCN from Bill’s transaction
>Send 3.32 ada to Barney
>Send 2 JCN to Barney
–Use 0.34 ada as the transaction fee

Barney has volunteered to take on the debt of -0.34 debt, in doing so validating Bill’s transaction. All fees were technically paid in ada, however, the way Bill sees it, he only paid using JCN.

If Barney wants the 2 JCN, he must also accept the -0.34 ada. They cannot be separated. Note that since two transactions were needed for this process to work, the total amount of fees paid was double than normal, 0.68 ada. 

This means that the amount of JCN that Bill pays has to be greater than or equal to 0.68 ada to make it worth it for Barney. Since fees are relatively small on Cardano compared to other chains, doubling them shouldn’t be a major issue.

This system works as long as there are users who consider the asset ‘JohnCoin’ JCN to be of value. They will compete in a fair and open market to offer the best exchange rate for fees. Tokens not considered valuable are useless in this system and can’t be used to pay fees, but that’s the way it should be. 

**Research comes to life**

Babel fees is just one area where IOG are bringing research into reality. IOG research engineer Paulina Vinogradova presented the elegant solutions being considered, competitive analysis of other chains’ solutions, as well as some of the remaining challenges in this presentation.[^20] Babel fees will play a crucial role in the success of the partner chains rollout described earlier.

**February 27, 2021. Re: Babel fees.** CH:[^21]

> …basically, what that does is it gives every token issued on Cardano the ability to pay in the native asset, if there is a market for it. So it solves all the problems at the same time and you, as token issuers, now have your own network. It used to be that either you had to go borrow another network and pay in that network’s fees, or you had to launch your own network and build a network effect behind it. This is the third option. The space currently does not allow that to exist. There are some clever hacks here and there, but for the most part, it’s a new thing. It’s an elegant thing and it’s a thing that’s brought uniquely because of Extended UTXO.
>
> And that’s the magic of doing things correctly. When you do things correctly, it’s very easy to just innovate, and just add and say, ‘here you go’. What that means is we’re probably going to be the ultimate stablecoin platform for all the stablecoins because you pay the transaction fee in the stablecoin. You don’t have to pay 100 of Eth to send a dollar of Tether.[^22] you know that’s the point, and that’s what we’ve been looking for and that was just one of many things that came.

**Stablefees and tiered pricing**

IOG have talked about other similar features previously, like **Stablefees**,[^23] a mechanism to help make fees fairer with less volatility. The main idea behind Stablefees is to have a base price for transactions achieved by pegging to a basket of commodities or currencies.

Research has also been ongoing on a **tiered pricing** concept.[^24] The design’s major feature is dividing each block into three ‘tiers’ depending on the use case. Each tier is intended for various sorts of transactions and accounts for a certain proportion of the maximum block size. The tiers, as well as the proposed split being considered, are as follows:

- fair (50%)
- balanced (30%)
- immediate (20%)

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig102.png "figure 10.2")
<br>**Figure 10.2:** Tiered pricing: a block can be split into three tiers.

Those submitting transactions would define the tier of service they need in order to be included in a block. Although each transaction would be charged the lowest fee guaranteeing its inclusion, it still introduced the notion of elitism, or an element of plutocracy. 

These features have been in research for some time but will be crucial as DeFi activity on Carano spikes with the next bull market. As we saw with the emotionally charged debate on contingent staking, the proposed introduction of any of the above features will garner robust debate! Reading between the lines, it seems some of these tough decisions are being put on hold until the governance mechanisms are in place. They can only then be added to the protocol after an on-chain vote. It highlights the importance of getting a minimum viable government in place so the protocol can evolve and scale. 

## Djed stablecoin



**_The rest of the chapter will be uploaded soon..._**



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
[^16]: **HODL** is slang in the cryptocurrency community for holding the cryptocurrency rather than selling it. HODL can also mean ‘Hold On for Dear Life’ and refers to not selling, even during strong market volatility and poor market performance.
[^17]: **Game theory** is the study of mathematical models of strategic interaction in between rational decision-makers. It has applications in all fields of social science, as well as in logic and computer science. Originally, it addressed zero-sum games, in which each participant’s gains or losses are exactly balanced by those of the other participants. Today, game theory applies to a wide range of behavioral relations and is now an umbrella term for the science of logical decision making in humans, animals, and computers.
[^18]: Roundtable with Charles Hoskinson and Alex Chepurnoy | Ergo Pulse, youtube.com/watch?v=k9a3SYV6FJA
[^19]: **Spot trading** is a continuous process of buying and selling tokens and coins at a spot price for immediate settlement. The trader usually intends to gain profits from market fluctuations
[^20]: An **atomic swap** is an exchange of cryptocurrencies from separate blockchains. The swap is conducted between two entities without a third party's involvement. The idea is to remove centralized intermediaries like regulated exchanges and give token owners total control
[^21]: Babel fees via limited liabilities, youtube.com/watch?v=iJEmRZ6leXE
[^22]: Surprise AMA 02/26/2021, youtu.be/6eD_rnII3ms?t=42
[^23]: **Tether** (ticker USDT) is a cryptocurrency that is hosted on the Ethereum and Bitcoin blockchains, among others. Its tokens are issued by the Hong Kong company Tether Limited, which in turn is controlled by the owners of Bitfinex. Tether is called a stablecoin because it was originally designed to always be worth US$1.00, maintaining $1.00 in reserves for each tether issued.
[^24]: Stablefees and the Decentralized Reserve System, iohk.io/en/blog/posts/2021/06/10/stablefees-and-the-decentralized-reserve-system/
[^25]: Network traffic and tiered pricing, iohk.io/en/blog/posts/2021/11/26/network-traffic-and-tiered-pricing/
[^26]: Pegging means attaching or tying a currency's exchange rate to another currency
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
