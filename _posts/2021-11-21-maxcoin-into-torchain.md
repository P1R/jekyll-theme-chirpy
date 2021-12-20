---
title: Maxcoin integration into Thorchain
author: p1r0
date: 2021-11-21 18:30:00 +0800
categories: [Research, Resources]
tags: [Developers, Thorchain, Resources, Research]
math: true
---

The propose of this document is to setup a methodology  to get maxcoin blockchain linked and functional to Thorchain.

It is also important to note that since our philosophy is to be as decentralized as possible, we want to satisfy this by working with as many multiple true decentralized solutions as we can, which might include crosschain, 2nd Layers, DEXs, DEFIs and others.

---


## Overview

1. 1-way State Pegs allow syncing state from external chains
2. A State Machine to coordinate asset exchange logic and delegate redemptions
3. Bifröst Chain Client to convert redemptions into chain-specific transactions
4. A TSS protocol to enable distributed threshold key-signing[^fn-nth-1]


![](/assets/img/posts/thorchain-layers.png)


---


## Requirements to operate on ThorChain

1. Maxcoin wallet that integrates with Kubernetes and terraform
2. Create bifrost that works with Maxcoin
3. Have a testnet to also test it with the thorchain testnet
4. (optional) Provide Liquidity in Maxcoin(us) and Rune(us and miners)
5. (optional) Updates to wallets and some security audits by ourselfs en regards updates, maybe decentralize further


---

## Maxcoin wallet that integrates with Kubernetes and terraform

> We need and easy way to create the wallet of maxcoin (Kubernetes Image)-p1r0

THORNodes service the THORChain network, of which there is intended to be initially 99. Each THORNode is comprised of several independent servers in a cluster. All THORNodes communicate and operate in cooperation to create a cross-chain swapping network.[2]

To set up a node, you have three choices:

1. Set up manually (not recommended unless you are an expert)
2. Set up via Kubernetes (recommended)
3. Set up via Provider (coming soon)

### THORNode Stack
Each THORNode is comprised of 5 major components.[^fn-nth-2]
1. thornode  - this is a daemon that runs the THORChain chain itself and a HTTP server, that gives a RESTful API to the chain.
2. bifrost  - this daemon creates connections to remote chains (like Bitcoin, Ethereum, Binance, etc) to both observe activity on those chains (incoming/outgoing transactions), and also sign/broadcast outgoing transactions (moving funds on remote chains).
3. gateway : THORNode gateway proxy to get a single IP address for multiple deployments
4. midgard  - this daemon is a layer 2 REST API that provides front-end consumers with semi real-time rolled up data and analytics of the THORChain network. Most requests to the network will come through Midgard. This daemon is here to keep the chain itself from fielding large quantities of requests. You can think of it as a “read-only slave” to the chain. This keeps the resources of the network focused on processing transactions.
5. Full nodes - for every chain that is supported by the network, each THORNode operator will run their own full node of each chain (Bitcoin, Ethereum, Binance, etc).

### Terraform
Terraform is an open-source infrastructure as code software tool that provides a consistent CLI workflow to manage hundreds of cloud services. Terraform codifies cloud APIs into declarative configuration files. [Follow up the instalation](https://www.terraform.io/docs/cli/install/apt.html)

## Create bifrost that works with Maxcoin
> We need to create our own bitfrost for maxcoin -p1r0 


How THORChain works
The Bifröst Protocol: 1-way State Pegs Each node has a "Bifröst" service that deals with the nuances of connecting to each chain. Once nodes are 
synced, they watch vault addresses. If they ever see an inbound transaction, they read it and convert it into a THORChain witness transaction.
The witness transaction has the following parameters that are essentially the same for each chain, no matter the type:

```
type Tx struct {
  ID          TxID    `json:"id"`2
  Chain       Chain   `json:"chain"`3
  FromAddress Address `json:"from_address"`4
  ToAddress   Address `json:"to_address"`5
  Coins       Coins   `json:"coins"`6
  Gas         Gas     `json:"gas"`7
  Memo        string  `json:"memo"`8
}
```

THORChain processes each observed transaction and collects  signers  - essentially the keys of each node that reports a transaction that is 100% identical. Once a super-majority of nodes agree on a particular transaction, it moves from a  pending  state to a finalised state.[^fn-nth-1]

```
type ObservedTx struct {1
  Tx             common.Tx        `json:"tx"`2
  Status         status           `json:"status"`3
  OutHashes      common.TxIDs     `json:"out_hashes"` 4
  BlockHeight    int64            `json:"block_height"`5
  Signers        []sdk.AccAddress `json:"signers"` 6
  ObservedPubKey common.PubKey    `json:"observed_pub_key"`7
}
```


[bifrost repo](https://gitlab.com/thorchain/bifrost)

## Have a testnet to also test it with the thorchain testnet
> We might require a testnet to use also with the torchain testnet -p1r0

THORChain
Connecting to THORChain
How to connect to Midgard, THORNode and the base Tendermint layer.
The active node IP addresses can be queried from this endpoint:
https://testnet.seed.thorchain.info [^fn-nth-3]

The Network Information comes from three sources:

1. MIDGARD: Consumer information relating to swaps, pools, volume. DeFi dashboards, Wallets, Exchanges will primarily interact with Midgard.
2. THORNODE: Raw blockchain data relating to the THORChain state machine. THORChain block explorers will query THORChain-specific information here.
3. TENDERMINT: Tendermint standard data, used by all block explorers to query for base information.

## Provide Liquidity in Maxcoin(us) and Rune(us and miners) (optional) 
Based on roles the offical page says the following

There are four key roles in the system[^fn-nth-5]
:

* Liquidity providers who add liquidity to pools and earn fees and rewards
* Swappers who use the liquidity to swap assets ad-hoc, paying fees
* Traders who monitor pools and rebalance continually, paying fees but with the intent to earn a profit.
* Node Operators who provide a bond and are paid to secure the system

> Even if the liquidity providers are set as people that might want to earn fees and rewards, we might require to set an initial liquidity provided to setup at least a base price to start. [Roles](https://docs.thorchain.org/roles) -p1r0

## Updates to wallets and some security audits by ourselfs en regards updates, maybe decentralize further (optional) 


We might need to do updates to wallets and some security audits by ourselfs en regards updates, maybe decentralize further


> We might consider rebuild another genesis block and update this lines at the code, plus adding also the [dnsseed and/or some nodes](https://github.com/Max-Coin/maxcoin/blob/2af840024c8e81697252c2e24c268a8ce9165b8d/src/net.cpp#L1205) -p1r0

## Contact.

***Developers***

- [David Serrano](https://twitter.com/getmaxcoin)
- [p1r0](mailto:p1r0@nethunters.xyz)

## References

[^fn-nth-1]: https://docs.thorchain.org/technology 2021-10-27
[^fn-nth-2]: https://docs.thorchain.org/thornodes/overview 2021-10-27 

[^fn-nth-3]: https://www.terraform.io/docs/cli/install/apt.html 2021-10-28

[^fn-nth-4]: https://docs.thorchain.org/roles 2021-10-28

[^fn-nth-5]: https://docs.thorchain.org/developers/connecting-to-thorchain 2021-10-28

