# Chapter 4: Shelley (Consensus)

*‘If winter comes, can spring be far behind?’* ― Percy Bysshe Shelley

## The Scalability Challenge

Distributed systems are made up of a group of servers[^1] (nodes) that have agreed to execute a protocol, or a collection of protocols, to achieve a shared purpose. This objective might be as simple as distributing a file using the BitTorrent protocol,[^2] or decentralized storage.[^3] 

As more nodes join the network, the most efficient protocols acquire resources. If several peers are simultaneously downloading a movie file provided by BitTorrent, for example, it may be downloaded substantially quicker on average. Because peers both contribute and use up resources, the speed increases. When someone says a distributed system scales, they’re usually referring to this feature.

The problem with most existing blockchain protocols is that they were not built to be scalable in the first place. Blockchains, for example, are often a linked list of blocks that can only be added to. A blockchain protocol’s security and availability are dependent on numerous nodes having a complete copy of the blockchain data. As a result, N nodes must copy a single bit of data. Additional nodes place a burden on resources required. 

This is true for both transaction processing and gossip protocol[^4] across the system. Increasing the number of nodes in the consensus system does not increase transaction processing power. It simply indicates that more resources are required to do the same task. More network relaying means that more nodes must send the same messages to keep the whole network in sync with the most recent block.

Cryptocurrencies cannot grow to a worldwide network, comparable to older financial systems, due to their structure. Legacy infrastructure, on the other hand, is scalable and can handle orders of magnitude greater processing and storage power. Bitcoin is a relatively tiny network in comparison to its payment counterparts such as Visa, Mastercard, PayPal, etc and it is currently struggling to handle its present load.

The Ouroboros consensus protocol boosts scalability for Cardano. It allows for the decentralized election of a quorum of consensus nodes, which may then execute more conventional protocols to meet the demands of huge infrastructure providers like AWS, Google and Facebook.

For example, electing a quorum for an epoch implies there is a trustworthy group of nodes to keep the ledger up to date for a specified length of time. It is simple to elect many quorums at the same time and divide transactions among them.

## What is a Consensus Protocol?

A consensus protocol is a collection of rules and parameters that regulate the behavior of distributed ledgers: a set of rules that each network member must follow. There is no one central authority in charge of public blockchains. Instead, a consensus mechanism is employed to enable dispersed network users to agree on the network’s history as recorded on the blockchain - to achieve agreement on what has occurred and proceed from a single source of truth.

A single record is provided by that one source of truth. This is why blockchains are frequently referred to as ‘trustless,’ since trust is built into the protocol rather than needing users to trust one another. Unknown actors may communicate and trade with one another without requiring the mediation of a third party or the sharing of personal data.

Consensus is the method through which everyone participating in the blockchain’s operation comes to an agreement. There must be unanimity on which blocks to generate, which chain to use, and how to establish the network’s single state. Individual nodes examine the current state of the ledger and form a consensus using the consensus protocol Ouroboros. It has three key responsibilities: doing a leader check and deciding whether a block should be created, handling chain selection, and verifying blocks that have been produced.

Blockchains achieve consensus by enabling users to group transactions submitted to the system into blocks and add them to their own chain (sequence of blocks). The objective of the various consensus protocols is to determine who is permitted to generate a block? When? …and what to do in the event of a disagreement? For example, what if two participants add different blocks at the same time? There are many different types of consensus protocols,[^5] the main two being proof of work and proof of stake. Ouroboros is a consensus mechanism based on proof of stake that has been shown to have the same level of security as proof of work. 

## Ouroboros



**_To be uploaded soon..._**


[^1]: A server is a computer program or device that provides a service to another computer program and its user, also known as the client.
[^2]: **BitTorrent** is a communication protocol for peer-to-peer (P2P) file sharing which is used to distribute data and electronic files over the Internet. BitTorrent is one of the most common protocols for transferring large files, such as digital files containing movies or music.
[^3]:  Comparing 4 decentralized data storage offerings, techtarget.com/searchstorage/tip/Comparing-4-decentralized-data-storage-offerings
[^4]: A **gossip protocol** is a procedure or process of computer peer-to-peer communication that is based on the way epidemics spread. Some distributed systems use peer-to-peer gossip to ensure that data is routed to all members of an ad-hoc network. Some ad-hoc networks have no central registry and the only way to spread common data is to rely on each member to pass it along to their neighbors.
[^5]: 6 types of blockchain consensus mechanisms, essentialcardano.io/article/6-types-of-blockchain-consensus-mechanisms
[^6]:
[^7]:
[^8]:
[^9]:
[^10]:
[^11]:
[^12]:
[^13]:
[^14]:
[^15]:
[^16]:
[^17]:
[^18]:
[^19]:
[^20]:


[^89]:
[^90]:
[^91]:
[^92]:
[^93]:
[^94]:
[^95]:
[^96]:
[^97]:
