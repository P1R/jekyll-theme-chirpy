---
title: Maxcoin Governance DAO
author: David
date: 2021-12-15 16:31:00 +0800
categories: [Governance, DAO]
tags: [Governance, DAO]
math: true
mermaid: true
---
## DMAX


## Abstract

Maxcoin DAO has the goal to Develop and provide governance in the Maxcoin Project desitions, also it will help to make Maxcoin Project deflationary and incentive people to participate in the project decisions. In the following document we describe the generalities to make it work, technologies, protocols and processes.

 
## DMAX Features

* DAO verified 1 to 1 with the ERC20 token (DMAX)
* With a burn address, maxcoin (max) becomes deflationary.
* 10000 Maxcoin Minimum with a signed address going to the maxcoin burn address.
* DMAX becomes an Ethereum ERC20 Token.
* Anyone can participate in and have voting power based on token amount.
* To have a built-in incentives for dao users to verify maxcoins sent to burn address and verify DMAX tokens.

## Protocols and Tech Requirements

1. Maxcoin Project .
2. Ethereum Platform.
3. Aragon Client (DAO and Quadratic Voting).
4. Aragon Agent (DMAX management).

## Actors and Systems Use Case
* Maxcoin User 
* Maxcoin User Wallets (Maxcoin and Ethereum)
* Maxcoin DAO (Votes and verifies)
* Maxcoin DAO Tech (Aragorn, Ethereum Network, etc..)
* Maxcoin Blockchain Tech (Burning Address) 

> Note: ToDo... use case diagram

 
## Process Description

1. The Maxcoin user sends Maxcoin to the burning address
2. The Maxcoin user creates a request with the Transaction ID (TxID) at the Maxcoin DAO (based on Aragon client and Aragon Agent) And the Ethereum wallet address that will receive the DMAX token.
3. The Maxcoin DAO Members and already DMAX Holders will have the possibility to participate in the verification process. By doing Quadratic Voting (Aragon client module) we will generate a DMAX paired 1:1 with the burned Maxcoins, the DAO might take a small fee for voting and doing the process (this fee is to incentivize voters and get faster verifications)
4. The Maxcoin User gets DMAX in his  Ethereum Wallet.

## Sequence Diagram

![Sequence Diagram](/assets/img/posts/sequenceDiagramDAO.png)

```
sequenceDiagram
    MaxcoinBlockchain->>+BurnAddress: User Sends Maxcoin
    MaxcoinBlockchain->>+DAOMax: Notifies to DAO and sends DMAX address
    DAOMax->>+DAOMax: Creates a ballot for verifiers
    loop Verification Process
        DAOMax->>+BurnAddress: DAOMax Verifies transaction
        alt it was Approved
            DAOMax->>+DAOMax: Mints DMAX To The Onwers wallet - fee
            DAOMax->>+DAOMax: fee gets distributed to the DAO participants
        else it was not
            DAOMax-->>-MaxcoinBlockchain: Please verify
        end
    end

```

> Note Actors wheren´t added, hope someone can make it better soon... -P1r0
> the mermaid code is not getting interpreted... ToFix



## References

1. [Maxcoin DAO resources](/posts/dao-resources/)


## Contact.

***Developers***
- [David Serrano](https://twitter.com/getmaxcoin)
- [p1r0](mailto:p1r0@nethunters.xyz)


#### To Do

* Create the tokenomics section
* Add a conclusion section if required, but might require the DAOs review and further development.
