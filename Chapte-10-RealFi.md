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

Smart contracts allow for the creation of a wide range of unique tokens in the cryptocurrency sector. Babel fees are based on the idea of using your preferred token to interact with the platform. Similar to how you would interact with legacy financial systems, where you would use your local currency by just making a selection in a dropdown. ‘Babel fees’ convert the token you’re using to the one required by the platform for transactions or whatever trade you want to execute on the platform. IOG’s chief scientist, Prof Aggelos Kiavias,[^13] was ahead of the curve when introducing this concept early in 2021. IOG also produced a video whiteboard walkthrough[^14] on their ‘IOHK’ YouTube channel at the time. The paper ‘Babel Fees via Limited Liabilities’ was subsequently published in April 2022.[^15]

In most blockchains, it’s typical that a legitimate transaction must come at a cost to the sender. Without such a limitation, anybody may overwhelm the system with minor transactions, overflowing its capacity and leaving it worthless. On that basis, a common implication is that for any blockchain that supports user-defined currencies, paying transaction fees in such tokens should be forbidden. Instead, transactions should be charged a fee in the platform’s native token, which is seen as valuable by all the token holders (hodlers).[^16] It’s arguable that such a limitation is bad for adoption and interoperability with other blockchains and legacy systems. How are IOG planning to work around this shortcoming?

**eUTXO enables innovation** 

Cryptography and game theory[^17] have a history of making the seemingly impossible achievable. Cardano’s Extended UTXO (eUTXO) architecture enables a solution because of how native assets function on the platform. 

Tokens may be generated using a minting policy, and they are regarded similarly to ada on the ledger. Creating a valid transaction requires the consumption of one or more UTXOs. On Cardano, a UTXO may hold more than simply ada; it can also handle a token bundle containing numerous distinct tokens, both fungible and non-fungible. It is therefore feasible to use a single UTXO to construct transactions that transfer many distinct tokens. Ergo, underrated pioneers in the crypto space, have already delivered 15k outputs per transaction using EUTXO and rollups.[^18] 

The ledger’s transaction fees are priced in ada, using a function fixed as a ledger parameter. The costs necessary for a successful transaction may be anticipated accurately prior to execution, which is a key strength of Cardano’s EUTXO architecture. This is a unique property that other ledger configurations do not have. 

**How will Babel Fees work?**

Babel fees enable a transaction to announce an ada-denominated debt equal to the amount of fees the transaction issuer is required to pay. A transaction like this would be rejected by the ledger. However, it might be seen as an open offer in which the debt is taken on. Why would someone accept such a burden? To make this attractive, the transaction may give some quantity of token(s) to whoever covers the debt. The assumption being the token bundle is already existing in Cardano. This would be a one-to-one transaction between ada and the given token(s) at a fixed rate. 

Consider a block producer who notices a transaction like this. The block producer may generate a matching transaction and claim the tokens on offer by absorbing the debt and covering it with ada. The transaction with the debt, as well as its matching transaction, become admissible to the ledger as a group. The set of two transactions becomes priced in ada as a whole because of the debt absorption, and so it does not violate the ledgers’ accounting requirements in terms of ada fees. Therefore, the transaction with the debt is settled. 

Users can propose transactions priced in whatever token(s) they own and have them settle in the ledger as normal transactions if a block maker is ready to take them up on the spot trade.[^19] This shows how native assets, the EUTXO architecture, and the small but powerful change of adding liabilities in the form of negative values in token bundles can handle Babel fees, allowing users to price transactions in any token that the system supports natively.

For the above concept to work, Cardano must have liquidity providers who have ada and are ready to issue matching transactions. The ecosystem of thousands of stake pool operators (SPOs) are obvious initial candidates to make the market by advertising exchange rates for their preferred tokens, etc.

Following the introduction of native assets with the *Mary* hard fork, the possibility of negative amounts in token bundles can be incorporated into Cardano’s ledger rules. Aside from Babel fees, this opens up other use cases such as atomic swaps[^20] for spot transactions. It’s just another example of how Cardano innovates instead of forking and copying first and second-generation blockchains.

**A worked example**

Below is an example transaction in human readable format. This is about Bill, Ted and Barney exchanging ada and a new native token, JohnCoin (JCN). 

**Transaction**:<br>
<- Receive 20 ada from Bill<br>
-> Send 10 ada to Ted<br>
-> Send 9.66 ada to Bill<br>
*Use 0.34 ada as the transaction fee*<br>

Bill has received 20 ada in the past, so has a UTXO worth 20 ada in Daedalus. He takes that UTXO, sends 10 ada to Ted, 9.66 ada back to himself, and uses the leftover 0.34 as the transaction fee. For it to be a legitimate transaction, the inputs and the outputs must be equal, ie.  20 = 10 + 9.66 + 0.34


Now let’s look at a transaction that uses JohnCoin, JCN as well as ada.

**Transaction**:<br>
<- Receive 20 JCN from Bill<br>
<- Receive 4 ada from Bill<br>
-> Send 10 JCN to Ted<br>
-> Send 10 JCN to Bill<br>
-> Send 3.66 ada to Bill<br>
*Use 0.34 ada as the transaction fee*<br>

This time Bill wanted to send 10 JCN to Ted. He also had to include some ‘extra’ ada to cover the transaction fee. It worked fine, but it was inconvenient and not really sustainable if we were dealing with hundreds, or thousands, of transactions. 

Here’s how this same transaction would work with Babel fees.

**Transaction**:<br>
<- Receive 20 JCN from Bill<br>
-> Send 10 JCN to Ted<br>
-> Send 8 JCN to Bill<br>
-> Send -0.34 ada and 2 JCN to whomever takes on the debt<br>
*Use 0.34 ada as the transaction fee*<br>

This poses some questions:

How can Bill pay the 0.34 ada fee if he didn’t have any ada in Daedalus begin with? With babel fees, this isn’t a problem. So long as the inputs equal the outputs, the transaction is legit. The negative and positive ada in the outputs cancel each other out.

How can Bill send a negative amount of ada to just anyone, as a valid transaction? It isn’t a valid transaction until someone ‘volunteers’ to take on the debt. It has to be voluntary as no one can be sent negative ada without their permission. Why would anyone ‘volunteer’ to take on the debt? They would not only take on the debt, ie. the negative ada, they would also receive the additional 2 JCN.

So the first user to ‘volunteer’ to take on the debt, Barney in this example, will make a transaction as follows:

Transaction:<br>
<- Receive 4 ada from Barney<br>
<- Receive -0.34 ada and 2 JCN from Bill’s transaction<br>
-> Send 3.32 ada to Barney<br>
-> Send 2 JCN to Barney<br>
*Use 0.34 ada as the transaction fee*<br>

Barney has volunteered to take on the debt of -0.34 debt, in doing so validating Bill’s transaction. All fees were technically paid in ada, however, the way Bill sees it, he only paid using JCN.

If Barney wants the 2 JCN, he must also accept the -0.34 ada. They cannot be separated. Note that since two transactions were needed for this process to work, the total amount of fees paid was double than normal, 0.68 ada. 

This means that the amount of JCN that Bill pays has to be greater than or equal to 0.68 ada to make it worth it for Barney. Since fees are relatively small on Cardano compared to other chains, doubling them shouldn’t be a major issue.

This system works as long as there are users who consider the asset ‘JohnCoin’ JCN to be of value. They will compete in a fair and open market to offer the best exchange rate for fees. Tokens not considered valuable are useless in this system and can’t be used to pay fees, but that’s the way it should be. 

**Research comes to life**

Babel fees is just one area where IOG are bringing research into reality. IOG research engineer Paulina Vinogradova presented the elegant solutions being considered, competitive analysis of other chains’ solutions, as well as some of the remaining challenges in this presentation.[^21] Babel fees will play a crucial role in the success of the partner chains rollout described earlier.

**February 27, 2021. Re: Babel fees.** CH:[^22]

> …basically, what that does is it gives every token issued on Cardano the ability to pay in the native asset, if there is a market for it. So it solves all the problems at the same time and you, as token issuers, now have your own network. It used to be that either you had to go borrow another network and pay in that network’s fees, or you had to launch your own network and build a network effect behind it. This is the third option. The space currently does not allow that to exist. There are some clever hacks here and there, but for the most part, it’s a new thing. It’s an elegant thing and it’s a thing that’s brought uniquely because of Extended UTXO.
>
> And that’s the magic of doing things correctly. When you do things correctly, it’s very easy to just innovate, and just add and say, ‘here you go’. What that means is we’re probably going to be the ultimate stablecoin platform for all the stablecoins because you pay the transaction fee in the stablecoin. You don’t have to pay 100 of Eth to send a dollar of Tether.[^23] you know that’s the point, and that’s what we’ve been looking for and that was just one of many things that came.

**Stablefees and tiered pricing**

IOG have talked about other similar features previously, like **Stablefees**,[^24] a mechanism to help make fees fairer with less volatility. The main idea behind Stablefees is to have a base price for transactions achieved by pegging to a basket of commodities or currencies.

Research has also been ongoing on a **tiered pricing** concept.[^25] The design’s major feature is dividing each block into three ‘tiers’ depending on the use case. Each tier is intended for various sorts of transactions and accounts for a certain proportion of the maximum block size. The tiers, as well as the proposed split being considered, are as follows:

- fair (50%)
- balanced (30%)
- immediate (20%)

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig102.png "figure 10.2")
<br>**Figure 10.2:** Tiered pricing: a block can be split into three tiers.

Those submitting transactions would define the tier of service they need in order to be included in a block. Although each transaction would be charged the lowest fee guaranteeing its inclusion, it still introduced the notion of elitism, or an element of plutocracy. 

These features have been in research for some time but will be crucial as DeFi activity on Carano spikes with the next bull market. As we saw with the emotionally charged debate on contingent staking, the proposed introduction of any of the above features will garner robust debate! Reading between the lines, it seems some of these tough decisions are being put on hold until the governance mechanisms are in place. They can only then be added to the protocol after an on-chain vote. It highlights the importance of getting a minimum viable government in place so the protocol can evolve and scale. 

## Djed stablecoin

Cardano's primary stablecoin is named after *Djed*, the symbol of ‘stability’ in ancient Egypt and the symbolic backbone of the god *Osiris*, the god of the afterlife and resurrection. Djed is the first stablecoin to remove price fluctuation via formal verification. One of the major roadblocks to cryptocurrency adoption is its volatility. Transparency, immutability of data, and proven security of financial transactions are all advantages of blockchain technology. It is, however, more difficult to forecast crypto market fluctuations compared to fiat currencies. This makes it difficult to use cryptocurrency in everyday life.

A stablecoin is a cryptocurrency that is pegged[^26] to a basket of fiat currencies or a single fiat currency; commodities such as gold or silver; equities; or other cryptocurrencies. Stablecoins have built-in processes that maintain a minimal price variation from their target price, making them suitable for storing or exchanging value since the volatility is removed.

There are three main stablecoin types:

- Over-collateralized stablecoin backed by basket of other cryptocurrencies
- Algorithmic – the reserve (made up usually of one or more cryptocurrencies) is controlled by an algorithm
- Fiat-backed – a fiat currency reserve is used as collateral

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig103.png "figure 10.3")
<br>**Figure 10.3:** Stablecoin Classification

The price stability of certain stablecoins is jeopardized due to a lack of transparency and liquidity in their reserves. To solve these issues, IOG partnered up with COTI to implement Djed, a stablecoin contract, based on the Djed research paper.[^27]

**How stablecoins work underneath the hood**

Different processes contribute to the coin’s value stability and assist to minimize price fluctuations. The economic concepts of supply and demand underlie these systems. A popular technique is to back the stablecoin with a reserve of the pegged currency. If demand for ‘buy’ or ‘sell’ orders exceeds supply, the supply should be raised to minimize price swings. 

Stablecoin reserves are not usually kept in cash. They are usually invested in financial assets that provide interest, such as bonds. The operator raises funds from the returns on these investments. Price stability is maintained as long as the stablecoin is fully backed by reserves in the currency to which it is tied — and the operator can respond rapidly to fluctuations in demand.

The Djed stablecoin is intended to be a fiat currency-pegged asset with a governing algorithm. This method ensures a steady flow of funds. Djed isn’t only a dollar-denominated currency. It can function with any currency if oracles are available to provide the contract with the appropriate price index.

Djed’s reserve coin is called **Shen**, continuing with the ancient Egyptian theme. The Shen is said to be a symbol of both royalty and symmetry with a deep connection with infinity and permanence. 

**Risks**

Investments are often connected with stablecoin reserves. Due to the lack of liquidity in these investments, the operator may be unable to respond quickly to demand. In the short term, this weakens stability. Fiat-backed stablecoins have the disadvantage of requiring faith in the parties holding the reserves. Tether stablecoin (USDT) has already fallen as low as $0.92 in 2017[^28] due to a lack of reserve transparency and the ‘full-backing’ claim, as well as ineffective stabilizing safeguards.

When the underpinning asset is a cryptocurrency on a public blockchain, there are no transparency concerns. Furthermore, because of its automated and secure processes, the adoption of smart contracts allows the rapid and reliable implementation of stabilizing steps.

**What category of stablecoin is Djed?**

Djed is categorized as an over-collateralized stablecoin. The semantics are important because although Djed uses an algorithm, using an algorithm in itself is not a reason to be called an algorithmic stable coin. Djed uses external collateral (ada) which is unrelated to the protocol. Algorithmic stablecoins uses internal collateral, like in the case of Luna and UST. Djed is over-collateralized 4x to 8x, while algorithmic stable coins are usually only partially collateralized. Over-collateralized stable coins are traditionally less capital efficient, however, djed is different and actually fixes that with the Shen model with its symbiotic relationship. So djed is very capital efficient… one dollar worth of ada always equals one dollar worth of djed. 

Another difference is djed is always redeemable for the collateral, which is ada. Algorithmic stablecoins are not always redeemable. They are dependent on the value of the governance token. Djed stability is based on over-collateralization and not on the trust on the governance token, which is what you need to have if you're using an algorithmic stable coin.

Djed is a crypto-backed algorithmic stablecoin contract which functions as an autonomous bank. It works by minting and burning stablecoins and reserve coins, as well as holding a reserve of base coins. The contract uses the reserve to buy and sell stablecoins and charges fees that accrue in the reserve to keep the price of stablecoins pegged to a target price. Holders of reserve coins, who contribute funds to the reserve while accepting the risk of price volatility, are the beneficiaries of this revenue stream.

**Formal verification – the theory behind Djed**

Djed is the first stablecoin protocol that has been formally verified. Djed’s design and stability features are considerably enhanced by the use of formal methods[^29] in the programming process. Mathematical theorems are used to prove the properties using formal methods:

- Maintain the upper and lower bounds: the price will not move above or below the given price. Purchases and sales are not restricted in the typical reserve ratio range, and users have no motive to trade stablecoins on the secondary market outside of the peg range

- Peg stability during market crashes: the peg is maintained up to a certain limit, which is set by the reserve ratio, even when the price of the base coin falls drastically

- There is no insolvency since there is no bank involved, there is no bank contract to go bankrupt

- No bank runs because all users are treated equally and honestly, there is no reason for users to scramble to redeem their stablecoins

- Monotonically rising equity per reserve coin: the reserve excess per reserve coin is guaranteed to rise when users engage with the contract under certain circumstances. Reserve coin holders are certain to earn under these circumstances

- No reserve draining: under certain circumstances, it is impossible for a rogue user to carry out a series of acts that would deplete the bank’s reserves

- Bounded dilution: there is a limit on reserve coin holders and their profit can be diluted as a result of issuing more reserve coins.

**Versions**

Djed is available in two versions:

- Minimal Djed: This version aims to be as minimal, intuitive, and simple as possible while maintaining stability

- Extended Djed: this more sophisticated version offers greater stability. The adoption of a continuous pricing model and dynamic fees to further encourage the maintenance of an appropriate reserve ratio are the primary distinctions.

**Implementations**

IOG, Ergo, and Emurgo have been testing various techniques by implementing the Djed stablecoin contract.

SigmaUSD on Ergo was the first Djed stablecoin contract to be deployed. In Q1 2021, it was the first stablecoin to be implemented on a UTXO-based ledger. It contained a 1% charge for buying and selling transactions, as well as an hourly exchange rate update from an oracle. An unidentified user with a big quantity of ERGs (Ergo’s native currency) launched a reserve draining attack against the first version but the attempt was unsuccessful, and the perpetrator is said to have lost $100k.

To deter similar attacks, the first version of Minimal Djed was replaced with a version in which the charge was set to 2%, the oracle updated every 12 minutes, and each oracle update could only affect the price by 0.49 % unless the price difference was larger than 50%. This increased resistance to reserve draining attacks.

The IOG team has also implemented Djed in Solidity. One version employs the Ethereum blockchain’s native currency ether as a base coin, while the other can use any ERC20-compliant token as a base coin. These implementations have been launched to testnets for Binance Smart Chain, Avalanche Fuji, Polygon Mumbai, Ethereum Kovan,[^30] Ethereum Rinkeby, and RSK testnets so far. 

In addition, there is an OpenStar implementation. OpenStar is a Scala-based[^31] framework for private permissioned blockchains. Djed’s implementation with OpenStar is based on the concept of off-chain smart contract execution in order to create a stablecoin on Cardano that is not reliant on on-chain smart contracts.

**Djed implementation on Cardano**

Cardano’s Alonzo upgrade made Plutus smart contracts possible. Haskell runs on the Plutus Platform, which ensures a secure, full-stack development environment. Djed’s implementation has run in parallel, and assisted in, Plutus V2’s development.

Stablecoins and reserve coins are native assets in this implementation that are uniquely recognized by the hash of the monetary policy that regulates their minting and burning via the Djed protocol. This approach also expects that oracle data, such as the exchange rate, be delivered to transactions as signed data rather than being posted on the blockchain.

See the Djed paper or Bruno Woltzenlogel Paleo’s talk at Ergo summit 2021[^32] for more information about Djed stablecoin.

**COTI (currency of the internet)**

COTI is a longtime partner of IOG. The cFund[^33] for Cardano Developments made its first equity investment in COTI. It acts as a bridge between DeFi apps and the Cardano blockchain. COTI offers a solution called Ada Pay (adapay.finance), a payment gateway that allows retailers to accept ada payments with near-instant settlement. Unlike many financial products on the market, Coti’s treasury has always had transparent proof of reserves. 

Charles Hoskinson and COTI chief executive Shahaf Bar-Geffen revealed at the 2021 Cardano Summit that the COTI (coti.io) platform would be the official issuer of Djed.[^34] Stablecoins, according to the COTI development team, are a ‘killer app’ that will be used by a huge number of crypto users to settle payments and cover expenses. 

**Terra UST 2022 collapse**

Terra’s UST algorithmic stablecoin[^35] lost its peg[^36] to the US dollar in early May 2022. UST plummeted to 9c forcing Terra to dig deep into its Bitcoin reserves (~$1.3 billion) from its confirmed Bitcoin address[^37] in a desperate attempt to steady the ship. The dramatic collapse was summed up well by the Coin Bureau.[^38] 

Tether (USDT), one of the industry’s oldest stablecoins, has previously received criticism for its lack of transparency[^39] and reluctance to be audited. The suddenness of Terra’s collapse renewed skepticism on the viability of existing stablecoins and drove many[^40] to re-evaluate their views of Djed, and how it’s designed to be more resilient to similar hazards. Shahaf Bar-Geffen confirmed in subsequent update[^41] that Djed survived unscathed from the same tumultuous weekend for the crypto markets.  

**Why is Djed better than Terra Luna?**

2022 was a bad year for hacks and scams but the two big collapses, FTX and Luna, were due to human greed and corruption. The lack of self-regulation within the crypto industry was also a factor. Just as the crypto industry was tarnished by the FTX collapse, some are trying to tarnish Djed as guilty by association. Luna was also an algorithmic stablecoin, Djed also has an algorithm but that’s where the similarity ends. Djed is categorized as an over-collateralized stablecoin. 

There are years of academic research behind Djed’s algorithm. It started as the product of formal methods and has been battle-tested in simulations. Ergo have also implemented their version, SigmaUSD, which has withstood huge market volatility (90% drop) and maintained its peg. The theory behind over-collateralized stablecoins has repeatedly shown its resilience in adverse market conditions. 

Luna was not over-collateralized, Djed is over-collateralized by a healthy 4-8x ratio. Luna was backed by an asset, UST, which it had a direct correlation. The Luna ‘death spiral’ occurred because as UST lost its peg,[^42] the solution was to sell Luna. So, Luna’s price inevitably nose-dived creating a circular dependency. As the fiasco unfolded, the centralized entity behind Luna even tried to halt the network and add Bitcoin as an uncorrelated backing asset. 

Djed is backed by Ada, which is uncorrelated to Djed. There is no dependency, ada can exist without Djed. Ada has its own utility and ecosystem with plenty of liquidity. Djed is autonomous and decentralized running on its own smart contract. There is no human involvement, no central entity adjusting the reserve ratio. The dynamic ‘buy’ and ‘sell’ conditions are all set automatically. The fees go to Shen holders, not to the centralized issuer.

**Djed is launched**

COTI had already signed 40 partnerships with DEXs in the buildup to the long-awaited Djed launch. The private testnet scalability issues were addressed. The public testnet was launched in May 2022 and was followed by a full regress audit. Two security audits were conducted, which is due diligence for such a financial token. The public mainnet was launched in January 2023. 

**How does Djed work?**

At a high level, ada is backing the Djed stablecoin. Those who have Djed are the first to receive from the liability pool. They will always get back one dollar for their Djed. This is the safety mechanism in the system, it is over-collateralized, so Djed holders get the priority. On top of this, there is an equity pool created by those who provide liquidity and receive Shen in return.  

I send Ada to the smart contract, I get Djed back in return. If I want my ada back, I can send Djed back to the smart contract and get back ada. If I want to enjoy some upside while accepting more risk, I mint Shen by sending ada to the smart contract and burn it when I want to take my upside out. The process is autonomous, managing itself without any human involvement.

*400-800%*

Within the ratio of 400-800%, ie. 4x – 8x worth of ada to dollar ratio, this is the optimum range. You can mint and burn Djed, you can mint and burn Shen… 

*Above 800%*

Above 800% (8x), you can mint and burn Djed as much as you like, however, you cannot mint Shen anymore. For example, Shen holders are rewarded for the risk they take on early on. They are providing liquidity when needed. Otherwise, everyone might just wait until the ratio goes over 800% to mint Shen. The fact that you can’t mint Shen over 800% effectively protects Shen holders who minted it earlier. 

*Under 400%*

You can't mint Djed because there is not enough collateral. You can just burn Djed, and in doing so, raise the ratio. Within this range, you can send ada to the smart contract get Shen back. Under 400% (4x), you mint Shen but you can't burn it. This is the risk Shen holders take on, they can’t burn it (withdraw) below 400%. Shen holders must wait until there is more ada in the smart contract and the reserve ratio rises above 400% (4x).

![alt text](https://github.com/johnnygreeney/CardanoForTheMasses/blob/main/images/fig104.png "figure 10.4")
<br>**Figure 10.4**: Djed reserve ratio.

Despite its promising beginnings, Djed has faced some challenges, with its reserves dwindling to 356%. It saw something of a revival in late 2023 as Djed surged above[^43] 400% again allowing users the opportunity to mint and burn both $DJED and $SHEN. It's likely Djed is here to stay and will be reliable, however, it will need to be complemented by other stablecoins on Cardano. 

**Other Stablecoins on Cardano**

In April 2022 **WingRiders** launched with their DEX also bringing wrapped stablecoins[^44] (USDC and USDT) and liquidity through the Milkomeda bridge.

At the 2022 Cardano Summit, James Wager of Indigo Labs announced **iUSD**. iUSD is pegged to the median value of USDC (USD Coin), TUSD (TrueUSD), and USDT (Tether); this design allows iUSD to maintain its peg even if one of these three stablecoins depegs. 

Also in Lausanne, Vineeth Bhuvanagiri (Director of Emurgo Fintech) announced Anzens, a product suite to bridge the gap between DeFi, RealFi and TradFi (traditional finance). The first product will be a **USDA**, a fiat-backed stablecoin. It will operate by minting or burning USDA coins at a fixed exchange rate of 1 USDA to 1 USD based on user demand, ensuring that each USDA coin is backed by a corresponding US dollar held by a regulated US banking partner. In time, Emurgo will expand beyond the tokenization of dollars to other currencies and real-world assets. 

In his talk,[^45] Bhuvanagiri highlighted the savings in fees when using Cardano’s native asset standard. By contrast, Ethereum’s smart contract-based model requires more funds for gas (transaction) fees when moving funds around in USDC and USDT. USDC (USD Coin) and USDT (Tether) are centralized stablecoins, issued by private entities who charge hefty fees, primarily based on Ethereum.

**Mehen** is creating the **USDM** fiat-backed stablecoin for Cardano. Mehen claims that they will revolutionize the space with unmatched transparency, adaptability, and security. They claim USDM is not just another stablecoin. Unlike some centralized stablecoins on other blockchains, which can be frozen or taken off you by authorities, $usdm will be a Cardano native asset which cannot be frozen.  ‘$usdm is as native as $ada’ is a bullish claim, watch this space. 

**IOG launches dedicated Stablecoin venture**

In late 2023, IOG announced a new spin-off company which will focus solely on stablecoins. W. Sean Ford has been appointed as the CEO and David Markley as COO. Both worked at Algorand Inc who have had some success[^46] implementing stablecoin projects in the Marshall Islands and Brazil amongst others, as well as working with the Bank of Italy. Stablecoins is an area Charles Hoskinson has been researching and developing since 2013 with BitShares, and has expressed frustration trying to negotiate with some ‘pay to play’ centralized stablecoins.[^47] 

It will be interesting to see what impact the new venture has on an area some consider a weak spot for Cardano. At the Dubai Cardano Summit, an expert panel[^48] voiced their concerns that iUSD is not reliable enough to keep its peg, while also doubting Djed's ability to scale, as although it keeps its peg, it's not capital efficient. 

## How EUTXO copes with impermanent loss

Impermanent loss[^49] is a downside to those providing liquidity to a DEX. It can be a confusing term for newcomers.

The automated market maker (AMM) and order book are the most common architectures used to run DEXs (decentralized exchanges). AMMs are straightforward to build, and this architecture has subsequently become the standard for account-based chains. However, there are several drawbacks with this design, ‘impermanent loss’ being one of them.

Cardano employs the EUTXO model, which is deterministic, making it more predictable than the account-based model in terms of impermanent loss. The term ‘impermanent’ is a little deceptive because a drop in token price might only be transitory, and the price could climb again depending on market conditions. Because the price corrected upwards, the loss would be transient (impermanent). All that matters is the dollar price when you withdraw. If it’s lower than the price you bought at, then obviously the ‘loss’ becomes permanent. Ada peaked at $1.20 in the 2018 bull run.[^50] It plummeted then rose to an all-time high of $3.10 in Sept 2021. Volatility is to be expected in an immature industry, pricing emerging technology.

With light-touch regulation, it’s arguable that ‘impermanent loss’ is an inevitable risk for liquidity providers[^51] in the ‘wild west’ of crypto trading exchanges. If the loss exceeds the trading fees collected, the liquidity provider bears a loss, which could have been avoided if they had kept their tokens. It's also common that while liquidity providers may not lose money, their earnings may be lower than if you had simply retained the tokens.

**AMM**
 
The Automated Market Maker (AMM) DEX architecture offers smart contract-based automated trading of crypto pairs. With Ethereum being the dominant smart contract platform to date, naturally most pairs are between Ethereum tokens and stablecoins.

Liquidity pools enable users to pool their assets into smart contracts, which effectively power AMMs. The more liquidity in the pool, the more reliable the trading environment for traders on the DEX with which the pool is affiliated, and naturally, the more transaction fees the liquidity providers earn. Liquidity pools provide the liquidity on both sides of a trade. The pool uses an algorithm to determine the price of an asset based on its availability in the pool.

So AMMs are solely dependent on their liquidity providers to provide sufficient pool size to ensure trading is fair and reliable. Liquidity providers are more commonly known as ‘market makers’ in traditional finance.

IOG has several papers[^52] on the importance of the right incentives[^53] in cryptocurrency space. Incentives are essential to motivate liquidity providers for DEXs to function reliably and fairly. Liquidity providers are incentivized by yield farming[^54] in this case.

**Order book**

The mechanics of order book architecture should be familiar to anyone working in the world of economics. It's a simple model to understand. The order book basically stores all buy/sell (asks/bids) orders and organizes them according to the asset's price when the traders place their orders. The asset can be exchanged if there is sufficient supply and demand.

Order book architecture is much more suited for EUTXO-based ledgers, such as Cardano and Ergo, because its design, together with EUTXO features, mitigates the impacts of impermanent loss.

The number of tokens in a liquidity pool, and the number of liquidity providers contributing to it, are variables when it comes to predicting and avoiding impermanent loss. If there is regular impermanent loss occurring, then pools are not viable and liquidity providers will naturally go to a more profitable rival pool(s). It can be a vicious circle, as it can be too late to salvage once a ‘crypto bank run’ occurs like what happened with the Terra Luna debacle.[^55]

To recap from earlier,

- UTXO-based blockchains don’t have accounts holding a balance. Users' wallets keep track of a list of unspent outputs corresponding with all of the user's addresses and determine the user's balance. Remember UTXO transactions are analogous to 'cash in cash out'. The EUTXO model includes a datum, which is contract-specific metadata. This is significant because it allows Cardano to accommodate multi-assets and smart contracts.
- Account-based model holds a coin balance in an account (protected by a private key or a smart contract). Assets are represented as balances inside users' accounts, with the balances being saved as a global state of accounts. Each node maintains its own state, which is updated with each transaction.

There are various major distinctions between the above models, but there is one that stands out. AMMs that operate on Account-based chains are more likely to employ the Constant Formula Market Maker (CFMM) pricing formula, which is one of the most widely used AMM algorithms. There are inefficiencies in this formula, such as it provides users with little to no privacy.[^56]

Also, the Total Value Locked (TVL)[^57] is dispersed throughout the whole price range, implying that an asset's price might be $1 or $100,000. CFMM pricing is unreasonable under this premise and does not represent actual market realities. Furthermore, deals with a low token volume tend to have a lot of slippage.[^58] While CFMM is a common feature for AMMs, these inefficiencies may cause liquidity providers' earnings to be impacted. What's more, this liquidity is prone to impermanent loss.

**EUTXO and order book DEXs mitigate impermanent loss**

The key advantages of EUTXO architecture in terms of security, determinism, parallelism, and scalability were discussed earlier. EUTXO features make Cardano a suitable platform for DEXs that use order book architecture, since it provides greater resistance to impermanent loss. This design has a number of advantages, one of which is the concentration of liquidity allocated within a custom price range. This feature improves liquidity efficiency while reducing impermanent loss.

**Global vs Local state**

Unlike Account-based blockchains, where each transaction outcome changes the global state, EUTXO-based blockchains verify transaction legitimacy at the transaction level, with the balance equal to the total of remaining UTXOs. EUTXO works at the local level.

This is not the case with account-based blockchains. Smart contracts and other actors constantly interact and impact the global state, resulting in the use of assets and resources, as well as the volatile fluctuation of gas prices. Transaction fees can be very unpredictable because of this, even spiking between the time a transaction is submitted and the time it’s verified. As a result, the chain may reject such a transaction, but the gas costs are collected nevertheless, potentially resulting in the user's wallet taking a hit. As transaction volumes increase and enterprise customers consider using the platform, this is a critical flaw for the likes of Ethereum.

Extortionate ‘gas’ fees are not an issue with Cardano’s EUTXO model, since transactions are verified and executed at the local state. This is made possible by adding a datum (supplementary contract-specific metadata) to the transaction. The datum is passed to the transaction’s validation logic, ensuring that EUTXO remains deterministic. This essentially guarantees that transaction costs are fixed and will not vary in the future. Another advantage of EUTXO and determinism is that bad actors cannot reshuffle transactions, which is a danger with Account-based models.

A key benefit of transaction validation being local is that it allows for a high degree of parallelism. Account-based chains can't do this since transactions must be handled sequentially.

Cardano has met with some criticism for being too conservative by its competitors.[^59] Rather than ‘move fast and break things’, Cardano has been implemented carefully with scalability and performance addressed only after a secure network and consensus protocols were established. As the enhancements introduced at Vasil take hold, we have seen a raft of DEXs launch on Cardano such as Genius Yeild, Axo, DexHunter among others.[^60]  

## Certified dApps on Cardano


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
[^27]: Zahnentferner, Kaidalov, Etienne, Díaz (2021) 'Djed: A Formally Verified Crypto-Backed Pegged Algorithmic Stablecoin', eprint.iacr.org/2021/1069.pdf
[^28]: Tether Price History and Everything You Need to Know, rain.bh/learn/tether-price-history-and-information-you-need-for-tether-trading
[^29]: **Formal verification** is the act of proving or disproving the correctness of intended algorithms underlying a system with respect to a certain formal specification or property, using formal methods of mathematics. Formal verification can be helpful in proving the correctness of systems such as: cryptographic protocols, combinational circuits, digital circuits with internal Memory, and software expressed as source code.
[^30]: **Kovan** is a Proof of Authority (PoA) publicly accessible blockchain for Ethereum; created and maintained by a consortium of Ethereum developers.
[^31]: **Scala** is a general-purpose programming language providing support for functional programming and a strong static type system. Designed to be concise, many of Scala’s design decisions aimed to address criticisms of Java.
[^32]: Ergo Summit 2021 - Entering The New Era - Announcing AgeUSD & The Hardening Upgrade, youtube.com/watch?v=zG-rxMCDIa0&t=8366s
[^33]: A closer look at the cFund, iohk.io/en/blog/posts/2021/07/28/a-closer-look-at-the-cfund/
[^34]: Djed update, medium.com/cotinetwork/djed-development-update-421cea2c610b
[^35]: **Terra (LUNA)** is a Decentralized system focused on enhancing the DeFi space through programmable payments to drive adoption. The Protocol has a native Token, LUNA, and is backed by a host of fiat-pegged Stablecoin. By employing Stablecoin, Terra presents a payment infrastructure void of the shortcomings of traditional payment methods such as Credit card and old Blockchain-based payment systems.
[^36]: Terra UST collapse, coindesk.com/business/2022/05/09/ust-stablecoin-falls-below-dollar-peg-for-second-time-in-48-hours/
[^37]: Terra BTC address, bitaps.com/2c2daf15ff549f84faf3dde74da288727f4a63724c957bf83a2d263a97779f65/bc1q9d4ywgfnd8h43da5tpcxcn6ajv590cg6d3tg6axemvljvt2k76zs50tv4q
[^38]: Crypto Market EMERGENCY: UST, LUNA & BTC - What Gives?!, youtube.com/watch?v=x5v67Larlx8
[^39]: The tether controversy, explained, theverge.com/22620464/tether-backing-cryptocurrency-stablecoin
[^40]: Cardana ADA: I was wrong, youtube.com/watch?v=ew-qrNFKWtA
[^41]: COTI updates by Shahaf Bar-Geffen, COTI’s CEO, youtube.com/watch?v=453M7PjkIbc
[^42]: The Death Spiral: How Terra’s Algorithmic Stablecoin Came Crashing Down, forbes.com/sites/rahulrai/2022/05/17/the-death-spiral-how-terras-algorithmic-stablecoin-came-crashing-down/?sh=2e4307f371a2
[^43]: @cotinetwork, twitter.com/COTInetwork/status/1720163923658248297
[^44]: $ADA: DEX WingRiders Launches, Bringing USDC and USDT Stablecoins to Cardano Mainnet, cryptoglobe.com/latest/2022/04/ada-dex-wingriders-launches-bringing-usdc-and-usdt-stablecoins-to-cardano-mainnet/
[^45]: Stablecoins: what Cardano needs to bridge the gap between traditional finance and DeFi, youtube.com/watch?v=XGAH-TYl600
[^46]: Algorand stablecoin use cases, algorandtechnologies.com/news/stablecoin-use-cases-on-algorand
[^47]: @stakewithpride, x.com/StakeWithPride/status/1682401463631515649?s=20
[^48]: The Landscape of Stablecoins: Development and Considerations, youtu.be/-pKEZgn-eWw?si=z0iZJ1KZCiqSqHkT&t=435
[^49]: In DeFi, **impermanent loss** refers to the loss in value when investing liquidity in a liquidity pool compared to just holding tokens. The event occurs when the price of a user's tokens changes compared to when they deposited them in a liquidity pool. The larger the change is, the bigger the loss.
[^50]: A **bull market** or **bull run** is a state of a financial market where prices are rising. The term bull market is often used in the context of the stock market. However, it can be used in any financial market including cryptocurrencies.
[^51]: A **market maker** or **liquidity provider** quotes both a buy and a sell price in a financial instrument or commodity held in inventory, hoping to make a profit on the bid-offer spread, or turn. The U.S. Securities and Exchange Commission defines a ‘market maker’ as a firm that stands ready to buy and sell stock on a regular and continuous basis at a publicly quoted price.
[^52]: Kiayias,Koutsoupias, Stouka (2021) 'Incentives Against Power Grabs or How to Engineer the Revolution in a Pooled Proof of Stake System', arxiv.org/pdf/2111.08562.pdf
[^53]: Judmayer, Stifter, Zamyatin, Tsabary, Eyal, Gaži, Meiklejohn, Weippl (2021), ‘SoK: Algorithmic Incentive Manipulation Attacks on Permissionless PoW Cryptocurrencies’, eprint.iacr.org/2020/1614.pdf
[^54]: **Yield farming** is a DeFi term for leveraging DeFi protocols and products to generate high returns that sometimes reach over 100% in annualized yields 'when factoring in interest, token rewards, ‘cashback’ bonuses, and other incentives.' Yield farming is a way for cryptocurrency enthusiasts to maximize their returns. It typically involves users lending or locking up their funds using smart contracts. In return, users earn fees in the form of crypto.
[^55]: Is Do Kwon going to get arrested after Terra's LUNA price collapse?, fxstreet.com/cryptocurrencies/news/is-do-kwon-going-to-get-arrested-after-terras-luna-price-collapse-202205191033
[^56]: Chitra, Angeris, Evans (2021), 'Differential Privacy in Constant Function Market Makers', eprint.iacr.org/2021/1101.pdf
[^57]: The **(TVL) Total Value Locked** into a smart contract or set of smart contracts that may be deployed or stored at one or more exchanges or markets. This is used as a measurement of investor deposits. It is the dollar value of all the coins or tokens locked into a platform, protocol, lending program, yield farming program, or insurance liquidity pool.
[^58]: Slippage refers to the difference between the expected price of a trade and the price at which the trade is executed. Slippage can occur at any time but is most prevalent during periods of higher volatility when market orders are used.
[^59]: Criticism from Solana founder, twitter.com/IOHK_Charles/status/1532360549857693697?s=20&t=YIDNMde_QXHGEURpgZj8UA
[^60]: CardanoCube DEXs, cardanocube.io/collections/exchanges-dex
[^61]: Cardano 2021 Summit session on Certification, summit.cardano.org/sessions/smart-contract-certification-the-why-and-how
[^62]: Prof. Simon Thompson, iohk.io/en/team/simon-thompson
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
