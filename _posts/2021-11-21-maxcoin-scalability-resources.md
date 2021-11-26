---
title: Maxcoin Scalability Resources
author: p1r0
date: 2021-11-21 17:35:00 +0800
categories: [Research, Resources]
tags: [Developers, scalability, Resources, Research]
render_with_liquid: false
---

## SCALABILITY TRILEMMA

The Scalability Trilemma, a term coined by Vitalik Buterin (founder of Ethereum), refers to the tradeoffs that crypto projects must make when deciding how to optimize the underlying architecture of their own blockchain. 
The better question to ask is, which aspects of the blockchain does the project intend to optimize, and are these in line with its value proposition and use-case.[1]

The Trilemma claims that blockchain systems can only at most have two of the three properties[2]

Most blockchains currently lack the transaction performance required for global commercial use. Scaling this performance for global use is a huge challenge for developers. The trilemma itself refers to decentralization, security, and scalability - there is a degree of compromise for each whenever trying to improve one particular aspect.[3]

![](/assets/img/posts/maxcoin-scalability-resources.png)

### DECENTRALIZATION

Decentralization, as the word suggests, refers to the degree of diversification in ownership, influence and value in the blockchain. The important concept here is that it is the “degree of decentralization” — it is not a binary attribute. Ethereum is very decentralized; Eos is partially decentralized; Twitter is not at all decentralized. A common misconception is that networks can simply be labeled decentralized or not. Another one is that all blockchains are decentralized to the same degree. [1]

Decentralization (defined as the system being able to run in a scenario where each participant only has access to O( c ) resources, i.e. a regular laptop or small VPS)[2]

Decentralization: Decentralization, as the word suggests, refers to the degree of diversification in ownership, influence and value in the blockchain.[3]

##### Here are the pros and cons of decentralized protocols:

**Benefits**
* 	Decentralization, at a philosophical level, aims to bring power back to the community. By using a blockchain, where the rules of governance are literally codified and cannot be edited, one can maximize distribution of influence, wealth and ownership across the community.
* 	The more decentralized a system, the more secure (typically). There is no central point of failure or hack. There are, however, certain ways to hack even the most decentralized systems.

**Costs**
* 	Decentralized protocols like Bitcoin or Ethereum often use PoW mining to produce new blocks. This form of mining requires validators to solve difficult hash puzzles. As a result, this not only uses vast amounts of energy, but also compromises on performance and speed. This can be problematic for use-cases that require high throughput.
* 	The downside to leaving disputes up to the community, is that there is no central moderator. For certain use-cases, like Social Media, this would enable the publication of hate speech or fake news, for example.
* 	It is hard to shut down a decentralized blockchain, as there is no centralized server or party. While also stated as one of the core benefits, in a scenario where a destructive use-case were to arise, this would cause a problem that would be hard to resolve, apart from by the community itself.[1]

### SECURITY
Security refers to the level of defensibility a blockchain has against attacks from external sources. Internally, or within the blockchain itself, it’s a measure of how immutable the system is to change.[1]
Security (defined as being secure against attackers with up to O(n) resources) [2]
Security: Security refers to the level of defensibility a blockchain has against attacks from external sources.[3]

* 50% > Attack — an entity (or set of entities) that owns more than 50% of the total tokens outstanding, effectively owns the network
* 	Sybil Attack — an entity (or set of entities) could forge multiple (hundreds, thousands or more) identities on a system in order to effectively control a significant stake in ownership and/or decision making of the network
* 	Penny spend Attack — an entity (or set of entities) that flood the network with low-value transactions in order to stop the network from running
* 	Distributed Denial of Service Attack (DDoS) — occurs when there is intent to disrupt traffic in a network by flooding the network with malicious transactions
* 	Collusion Attack — one or more entities (or nodes) decide to collude together to perform some malicious operation(s) on the network

**Benefits**
	The primary benefit of robust security is that the blockchain is less vulnerable to attack. This is ideal for applications that require sovereign grade security and deal with confidential data. Anything in the realm of financial services would likely require the highest degree of security. Even crypto exchanges — one of the biggest targets of hackers — would be far better suited to deal with such attacks if built on a blockchain. (Indeed, we discuss the prospect of a new set of dApps — decentralized crypto exchanges — as one of the more promising ideas for future dApps on Eos).
**Costs**
	There are no downsides to maintaining robust security, but in order to do so there are a few second-order effects that are concerning. Many secure blockchain networks utilize PoW protocols — these require complex hash puzzles to be solved prior to block production — but more importantly, these protocols use up an immense amount of computing power and energy. Consequently, this reduces throughput and increases network latency, a strong deterrent for many potential users, that are used to near-instantaneous transaction times on centralized networks. This is still a worthwhile tradeoff for platforms that put a premium on security, but for ones that attempt to optimize user experience, this is certainly a strong consideration.
    
### SCALABILITY
The degree of scalability is important because it dictates the eventual capacity of any network. Put another way, it determines the upper limit on how large a network can grow. It is perhaps the most important question to think about when evaluating a network — how many users can this network sustain? Bitcoin currently has between 2.9 to 5.8 million wallet holders; scalability and decentralization can co-exist, but security risks become greater. Developers will choose the platform that best suits their needs, and users will choose the platforms that function best, according to them. Some users may be willing to sacrifice security for scalability; others, scalability for security. [1]

Scalability (defined as being able to process O(n) > O(c) transactions)[2]

Scalability: The scalability problem is the limited rate at which a blockchain network can process transactions. [3]

**Benefits**
* 	Scalability ensures that the application runs quickly and that it can support a high volume of transactions. As we mentioned, this is especially useful for audio/video streaming sites, gaming, and social media.
* 	The application is less likely to break down if user demand is greater than originally planned (Cryptokitties, for example, which was run on Ethereum, was not very scalable and ran into major issues because of this.

**Costs**

The costs to achieving infinite scalability primarily regard security. Almost all of the above security risks become greater with a network of massive scale. In addition, quickly growing networks will require a fast consensus mechanism, in order to validate more transactions while delivering the same speed to individual users. This can only occur in Proof of Stake or Delegated Proof of Stake. This compromises decentralization. If the protocol is Proof of Work, the hash puzzles or mining algorithms would need to be easier in order to have a commensurately fast validation process. This compromises security, and also decentralization to an extent (mining pools would thrive if hash puzzles were made easier).[1]

## SCALING TYPES

### Layer 1 solutions

#### Segregated Witness (Segwit)

Segwit is a protocol upgrade for Bitcoin that changes the way and structure of how data is stored. By removing the signature data for each transaction, it frees up more space and capacity for more transactions to be stored in Bitcoin’s 1MB-capacity blocks. The signature data – the digital signature that verifies the ownership and availability of the sender’s funds – makes up almost 70% of the entire space of a transaction. Therefore, removing it would save tremendous space that allows more transactions to be included in the block. Segwit has already been implemented in Litecoin. [4]

Segregated Witness or SEGWIT is also another notable addition among solutions to scalability of blockchain among first layer solutions. SEGWIT is basically a protocol improvement in the Bitcoin blockchain network, focused on modifying the manner and structure of data storage. It helps in the removal of signature data associated with each transaction, thereby opening up more capacity and space for storing transactions. It is important to note that the digital signature for verifying ownership and availability of the funds of the sender, takes around 70% of the whole space in a transaction. Removal of the digital signature could clear up more space for adding more transactions. [5]

#### Sharding (might be better with PoS)

Ethereum 1.0 can only process 7-15 transactions per second, the goal of sharding is to partition all network computational resources into shards, so that a node (a single computer as a peer connected to the network) doesn’t have to process (download, compute, store, read) every transaction in the history of the blockchain, in order to make a new transaction (write and upload) or otherwise participate in securing and using Ethereum; rather a node can just participate in a single shard, or more if it so chooses. Multiple shards are handled separately by different subsets of securing participants, aka securitors (which include notaries, proposers, miners and validators. The primary goal is a massive scalability improvement, potentially exponential in phase 6 of the roadmap; and probably at least a 100 fold increase in transactions per second with earlier phases. Quadratic sharding involves having shards at a depth of at most 1 from the main chain, that is, there are no shards within a shard, or a manager shard managing sub-shards; whereas exponential sharding has shards within shards, recursively.
Each one of the shards (likely 100 live in phase 1) will have as high a capacity (and likely more with phase 1) than the current existing Ethereum chain. A smart contract will exist on the main chain, called the sharding manager contract, which manages how data and transactions in shards are accepted as valid by the main chain, via notaries voting on the validity and data availability of collations (collections of data and transactions, analogous to blocks, but where they occur more frequently than blocks) in shards, and proposers proposing blobs (analogous to transactions but without execution in phase 1) which are collected into collations.[6]

Sharding is the future of Ethereum scalability, and it will be key to helping the ecosystem support many thousands of transactions per second and allowing large portions of the world to regularly use the platform at an affordable cost. However, it is also one of the more misunderstood concepts in the Ethereum ecosystem and in blockchain ecosystems more broadly. It refers to a very specific set of ideas with very specific properties, but it often gets conflated with techniques that have very different and often much weaker security properties. The purpose of this post will be to explain exactly what specific properties sharding provides, how it differs from other technologies that are not sharding, and what sacrifices a sharded system has to make to achieve these properties.[7]

* Traditional blockchains - including Bitcoin, pre-PoS/sharding Ethereum, Litecoin, and other similar chains. These rely on every participant running a full node that verifies every transaction, and so they have decentralization and security, but not scalability.
* 	High-TPS chains - including the DPoS family but also many others. These rely on a small number of nodes (often 10-100) maintaining consensus among themselves, with users having to trust a majority of these nodes. This is scalable and secure (using the definitions above), but it is not decentralized.
* 	Multi-chain ecosystems - this refers to the general concept of "scaling out" by having different applications live on different chains and using cross-chain-communication protocols to talk between them. This is decentralized and scalable, but it is not secure, because an attacker need only get a consensus node majority in one of the many chains (so often <1% of the whole ecosystem) to break that chain and possibly cause ripple effects that cause great damage to applications in other chains.
*   Sharding is a technique that gets you all three. A sharded blockchain is:
* 	Scalable: it can process far more transactions than a single node
* 	Decentralized: it can survive entirely on consumer laptops, with no dependency on "supernodes" whatsoever
* 	Secure: an attacker can't target a small part of the system with a small amount of resources; they can only try to dominate and attack the whole thing

* 	Scalable verification of computation
  We can break up the 51%-attack-proof scalable validation problem into two cases:
    * 	Validating computation: checking that some computation was done correctly, assuming you have possession of all the inputs to the computation
    * 	Validating data availability: checking that the inputs to the computation themselves are stored in some form where you can download them if you really need to; this checking should be performed without actually downloading the entire inputs themselves (because the data could be too large to download for every block)
* Validating a block in a blockchain involves both computation and data availability checking: you need to be convinced that the transactions in the block are valid and that the new state root hash claimed in the block is the correct result of executing those transactions, but you also need to be convinced that enough data from the block was actually published so that users who download that data can compute the state and continue processing the blockchain. This second part is a very subtle but important concept called the data availability problem; more on this later.
* Scalably validating computation is relatively easy; there are two families of techniques: fraud proofs and ZK-SNARKs.[7]


#### Dynamic block size (Might Require RandomX or Cryptonote)

In the height of the 2017 cryptocurrency boom, Bitcoin was flooded with transactions, and the fees skyrocketed for those that wanted to be included in the next block, or any near-future block for that matter. Those who were unwilling to pay high fees saw their transactions pushed back for hours, days, or even drop out of the queue altogether.
This was a harrowing insight into how Bitcoin would fare if the oft talked about ‘mass adoption’ were to occur. If Bitcoin was to be used by the masses, things would be even worse than in 2017, and Bitcoin would be inaccessible to anyone but the wealthy, simply because the throughput is small due to a fixed block size, causing the fee market to take over.
Monero foresaw this and wanted to do something different. So the Monero developers implemented a dynamic blocksize.
Basically, Monero also has a block size cap, but it’s a soft cap. When the line of waiting transactions gets too long, the miners can increase the size of the blocks. With our train analogy, you can imagine adding more train cars to fit the extra passengers. After the queue is empty the blocks shrink back to their original size going forward.
If this seems like a neat idea, it seems reasonable to ask why Monero is the only cryptocurrency that has implemented this. Why not add it on Bitcoin so as to put a stop to the throughput issues?
Unfortunately, this is not possible. There are several reasons why, and we’ll do our best to explain.
It's always in a miner's best interest to have large blocks. With large blocks they can fit in more transactions, and make more money off of the fees, as well as the block rewards. This has the potential to lead to spam attacks, where someone sends many small transactions, with small fees, to bloat the chain. Miner's would just raise the block size include them all because money is money, no matter how small. This would lead to consistently large blocks with little economic benefit. Bitcoin solves this by artificially restricting the block size, thereby generating a fee market. Spam attackers would have to outpay the other users in fees, and it is no longer cheap. But this means blocks get full leaving some transactions waiting as mentioned above.
So how can Monero have dynamic blocksizes but avoid spam attacks? The answer is simple, but clever. A penalty on the block reward is introduced when a block is bigger than normal. If a miner wants to increase the blocksize, the reward they get from finding that block will be less than they would otherwise receive. So they will only increase the blocksize when the paid transaction fees of the users outweigh the lost portion of the block reward. For example, if the miner would lose 0.5 XMR by raising the block reward, and the sum of the paid transaction fees would be 0.4 XMR, then there would be a net loss of 0.1 XMR if they were to raise the size, so they wouldn’t do it. Conversely, if the total transaction fees added up to 0.7 XMR, then there would be a net gain of 0.2 XMR, even though they lose the 0.5 XMR from the block reward penalty, so the miner will increase the size.
These dynamic blocks, allow the network to grow organically, without aritifically restricting the blocksize to make a forced fee market, while still avoiding spam attacks. There are several more angles we can view this idea from, and more reasons why it wouldn't be possible to add to Bitcoin, but for now, we hope that the reader has an understanding of how Monero sidesteps several of the problems in Bitcoin and its derivatives, and how it plans to scale its throughput into the future.[8]

The block size of Monero coin cryptocurrency is elastic which is based upon the median of the sizes of the preceding n number of blocks. The maximum size of any of the blocks is twice of the ongoing medium size. Hence the miners repeat 4 times incrementing penalization from the reward of the block for making the block bigger than the ongoing median which is prevalent in the Monero blockchain. The minimum of the medians of the block sizing is currently set to 20 kilobytes. What it means is that without the need of dynamic block sizing to start any of the blocks which is present within the Monero blockchain can be made to expand up to the maximum of 20 kilobytes without leaving any of the penalty over the individual who is mining Monero coin.

However, there is a proposal in the pipeline which suggests that the block size of the Monero coin cryptocurrency should be incremented to the memory size of 40 kilobytes which shall help to retain the optimum time-barring of the starting capacity of the block at the same hashing rate. Another proposal was put in which proposed to increment the block size of Monero blockchain to 60 kilobytes because it was observed that a larger amount of mixing of the sizes shall be manufactured which shall result in the more breakages in the transactions and slip transactions which shall be solely inconvenient for the people who are trading in Monero and who are accepting payments in Monero coin cryptocurrency. It was also and envisioned that ultimately it shall be difficult for the merchants to adopt this method as a major fraction of the people who are very positive about the Monero coin cryptocurrency have only got a single method of payment installed.

Therefore they shall be required to manually process the transactions which may arise due to the split payments. The optimum size of 60 kilobytes, therefore, was observed as to be allowing most of the routine payments getting easily handled without the risk of getting split. Therefore, the size of 60 kilobytes is thought to be great for the overall long-term adoption of the Monero coin cryptocurrency. [9]

> Todo: Decentralization that DPoS and RandomX can provide?

### Layer 2 solutions

#### BASED ON APPLICATION TYPES

1. 	Application specific (payment channels): lightning or plasma for example.
 
2. 	Arbitrary contracts executions ( zkrollups, optimisticrollups (easier implementations of smart contracts with OVM a EVM version, yet slower thank ZkSnarks))

#### BASED ON SCALABILITY VALIDATING COMPUTATION TYPES

Scalably validating computation is relatively easy; there are two families of techniques: fraud proofs and ZK-SNARKs.[7]

1. 	Fraud proofs are a system where to accept the result of a computation, you require someone with a staked deposit to sign a message of the form "I certify that if you make computation C with input X, you get output Y". You trust these messages by default, but you leave open the opportunity for someone else with a staked deposit to make a challenge (a signed message saying "I disagree, the output is Z"). Only when there is a challenge, all nodes run the computation. Whichever of the two parties was wrong loses their deposit, and all computations that depend on the result of that computation are recomputed.[7]

2. 	ZK-SNARKs are a form of cryptographic proof that directly proves the claim "performing computation C on input X gives output Y". The proof is cryptographically "sound": if C(x) does not equal Y, it's computationally infeasible to make a valid proof. The proof is also quick to verify, even if running C itself takes a huge amount of time.[7]

Computation based on fraud proofs is scalable because "in the normal case" you replace running a complex computation with verifying a single signature. There is the exceptional case, where you do have to verify the computation on-chain because there is a challenge, but the exceptional case is very rare because triggering it is very expensive (either the original claimer or the challenger loses a large deposit). ZK-SNARKs are conceptually simpler - they just replace a computation with a much cheaper proof verification - but the math behind how they work is considerably more complex.
There is a class of semi-scalable system which only scalably verifies computation, while still requiring every node to verify all the data. This can be made quite effective by using a set of compression tricks to replace most data with computation. This is the realm of rollups.[7]

***State channels/atomicswaps (Applications specific) vs plasma/lightning(Applications specific) vs rollups***
The three major types of layer-2 scaling are state channels, Plasma and rollups. They are three different paradigms, with different strengths and weaknesses, and at this point we are fairly confident that all layer-2 scaling falls into roughly these three categories (though naming controversies exist at the edges, eg. see "validium").

**How do channels work?**


Imagine that Alice is offering an internet connection to Bob, in exchange for Bob paying her $0.001 per megabyte. Instead of making a transaction for each payment, Alice and Bob use the following layer-2 scheme.
First, Bob puts $1 (or some ETH or stablecoin equivalent) into a smart contract. To make his first payment to Alice, Bob signs a "ticket" (an off-chain message), that simply says "$0.001", and sends it to Alice. To make his second payment, Bob would sign another ticket that says "$0.002", and send it to Alice. And so on and so forth for as many payments as needed. When Alice and Bob are done transacting, Alice can publish the highest-value ticket to chain, wrapped in another signature from herself. The smart contract verifies Alice and Bob's signatures, pays Alice the amount on Bob's ticket and returns the rest to Bob. If Alice is unwilling to close the channel (due to malice or technical failure), Bob can initiate a withdrawal period (eg. 7 days); if Alice does not provide a ticket within that time, then Bob gets all his money back.
This technique is powerful: it can be adjusted to handle bidirectional payments, smart contract relationships (eg. Alice and Bob making a financial contract inside the channel), and composition (if Alice and Bob have an open channel and so do Bob and Charlie, Alice can trustlessly interact with Charlie). But there are limits to what channels can do. Channels cannot be used to send funds off-chain to people who are not yet participants. Channels cannot be used to represent objects that do not have a clear logical owner (eg. Uniswap). And channels, especially if used to do things more complex than simple recurring payments, require a large amount of capital to be locked up.

**How does plasma work?**

To deposit an asset, a user sends it to the smart contract managing the Plasma chain. The Plasma chain assigns that asset a new unique ID (eg. 537). Each Plasma chain has an operator (this could be a centralized actor, or a multisig, or something more complex like PoS or DPoS). Every interval (this could be 15 seconds, or an hour, or anything in between), the operator generates a "batch" consisting of all of the Plasma transactions they have received off-chain. They generate a Merkle tree, where at each index X in the tree, there is a transaction transferring asset ID X if such a transaction exists, and otherwise that leaf is zero. They publish the Merkle root of this tree to chain. They also send the Merkle branch of each index X to the current owner of that asset. To withdraw an asset, a user publishes the Merkle branch of the most recent transaction sending the asset to them. The contract starts a challenge period, during which anyone can try to use other Merkle branches to invalidate the exit by proving that either (i) the sender did not own the asset at the time they sent it, or (ii) they sent the asset to someone else at some later point in time. If no one proves that the exit is fraudulent for (eg.) 7 days, the user can withdraw the asset.
Plasma provides stronger properties than channels: you can send assets to participants who were never part of the system, and the capital requirements are much lower. But it comes at a cost: channels require no data whatsoever to go on chain during "normal operation", but Plasma requires each chain to publish one hash at regular intervals. Additionally, Plasma transfers are not instant: you have to wait for the interval to end and for the block to be published.
Additionally, Plasma and channels share a key weakness in common: the game theory behind why they are secure relies on the idea that each object controlled by both systems has some logical "owner". If that owner does not care about their asset, then an "invalid" outcome involving that asset may result. This is okay for many applications, but it is a deal breaker for many others (eg. Uniswap). Even systems where the state of an object can be changed without the owner's consent (eg. account-based systems, where you can increase someone's balance without their consent) do not work well with Plasma. This all means that a large amount of "application-specific reasoning" is required in any realistic plasma or channels deployment, and it is not possible to make a plasma or channel system that just simulates the full ethereum environment (or "the EVM"). To get around this problem, we get to... rollups.

**Rollups**


Plasma and channels are "full" layer 2 schemes, in that they try to move both data and computation off-chain. However, fundamental game theory issues around data availability means that it is impossible to safely do this for all applications. Plasma and channels get around this by relying on an explicit notion of owners, but this prevents them from being fully general. Rollups, on the other hand, are a "hybrid" layer 2 scheme. Rollups move computation (and state storage) off-chain, but keep some data per transaction on-chain. To improve efficiency, they use a whole host of fancy compression tricks to replace data with computation wherever possible. The result is a system where scalability is still limited by the data bandwidth of the underlying blockchain, but at a very favorable ratio: whereas an Ethereum base-layer ERC20 token transfer costs ~45000 gas, an ERC20 token transfer in a rollup takes up 16 bytes of on-chain space and costs under 300 gas.[7]
The fact that data is on-chain is key (note: putting data "on IPFS" does not work, because IPFS does not provide consensus on whether or not any given piece of data is available; the data must go on a blockchain). Putting data on-chain and having consensus on that fact allows anyone to locally process all the operations in the rollup if they wish to, allowing them to detect fraud, initiate withdrawals, or personally start producing transaction batches. The lack of data availability issues means that a malicious or offline operator can do even less harm (eg. they cannot cause a 1 week delay), opening up a much larger design space for who has the right to publish batches and making rollups vastly easier to reason about. And most importantly, the lack of data availability issues means that there is no longer any need to map assets to owners, leading to the key reason why the Ethereum community is so much more excited about rollups than previous forms of layer 2 scaling: rollups are fully general-purpose, and one can even run an EVM inside a rollup, allowing existing Ethereum applications to migrate to rollups with almost no need to write any new code.[7]




#### In Resume
Application Specific solutions like PaymentChannels, Lightning/Plasma and atomic swaps might be useful for specific use cases in Maxcoin, for example; creating an atomic swap with other cryptocurrency and some Dexes that might use atomic swaps as a standar protocol for multichain operability. Another application might be also to develop an Ethereum/Polka/Cardano a DEFI model that might use some FraudProofs or ZKSnarks Model, but without the EVM. A last application is to create a ZKSnarks based model for a Mixer in order to provide Anonymity/Untraceability and thus Fungibility into the Maxcoin Currency.
   
In regards of Rollups

1. 	Zkrollups:  ValidityProofs, Faster (Cryptography methods, based on Zero-Knowledge proofs), requires lots of science behind, to get implemented correctly specially for a EVM implementation. it might be easier for a Application specific function, some heavy computation required. zkSync, zkTube, LoopRing(Application Specific), StarkWare
 
2. 	OptimisticRollups: FraudProofs (requires colateral and actors, also handle by DAO), Slower, DEFI models to implement faster transactions, but might need to add some values to it, a heavy comunity required. Optimism, OMG and arbitrum 

> Todo, Search rollups and the verification methods for them



## CONCLUSIONS FOR MAXCOIN

It's important to say that the biggest blockchains with larger communities are working in both first and second layer solutions, this is smart since right now their highest limitation is scalability with the high demand they have. 

Its is good for our research propose that we visualize a future like this for maxcoin and based on other blockchain experiences we follow up with some of these implementations before the demand of maxcoin grows, regarding security it is also important that Maxcoin as a cryptography enhanced tech keeps this main base and  follow up with zkRollups as second layer solution, while maintaining the highest security possible in the layer 1.  

The main discussion regarding the Maxcoin philosophies/priorities, as a purely enhanced technology based on earlier types of cryptography can be the security, by on other hand joining the smart contract world might also require scalability.

Finally, decentralization currently might be our weakest field, yet by keeping the current work on providing the tools and developing easier ways to distribute the maxcoin network,  bigger community might take care of this(still the demand of users is low and might not be a priority for now), plus looking forward on  1 layer solutions like changing the consensus mechanism that may also enhance the decentralization (PoS or RandomX), also there are some implementations for sharding that we might want to consider, but this might be only when the blockchain size reaches a huge size (still might be useful to have more nodes that have a full piece of the chain).

References:

[1] https://aakash-111.medium.com/the-scalability-trilemma-in-blockchain-75fb57f646df

[2] https://medium.com/logos-network/everything-you-know-about-the-scalability-trilemma-is-probably-wrong-bc4f4b7a7ef

[3] https://www.quora.com/What-is-the-blockchain-scalability-trilemma?share=1

[4] https://masterthecrypto.com/blockchain-scalability-solutions-crypto-scaling-solutions/

[5] https://101blockchains.com/blockchain-scalability-solutions/

[6] https://eth.wiki/sharding/sharding-introduction-r-d-compendium

[7] https://vitalik.ca/general/2021/04/07/sharding.html

[8] https://localmonero.co/knowledge/dynamic-block-size

[8] https://github.com/JollyMort/monero-research/blob/master/Monero%20Dynamic%20Block%20Size%20and%20Dynamic%20Minimum%20Fee/Monero%20Dynamic%20Block%20Size%20and%20Dynamic%20Minimum%20Fee%20-%20DRAFT.md

[9] https://www.hashgains.com/wiki/m/what-is-monero-coin-block-size



Further interesing info
**Scaling**
https://www.youtube.com/watch?v=BgCgauWVTs0
https://www.youtube.com/watch?v=7pWxCklcNsU

**ZeroKnowledge Proofs**
https://www.youtube.com/watch?v=HUs1bH85X9I
https://www.youtube.com/watch?v=OcmvMs4AMbM
