---
title: GPU (Nvidia) Mining Guide
author: p1r0
date: 2021-12-05 05:35:00 +0800
categories: [Miners, Guides]
tags: [Maxcoin, Miners, Guides, GPUs]
render_with_liquid: false
pin: true
---

by: https://twitter.com/graphics4crypto and https://twitter.com/mxjmpbean

## Getting Started:

- Download and unzip ccminer 8.19
- Open ccminer folder then create a text document ( Right click-> New-> Text Document).
- New Text Document -> Right click–> Rename-> MAXcoin-<poolname>.conf
- then (RightClick ->  Edit) copy & paste, where <poolname> is the name of the pool you wish to connect
- {
“algo” : “keccak”,
“url” : “stratum+tcp://pool_address:port”,
“user” : “username.workername”,
“pass” : “worker_password”
}
- Replace username.workername and worker password from your pool account.
- Replace from “url” : stratum+tcp://pool:port with the pool address you with to use.
- Save and close the file.
- Duplicate this file for other pools editing your username.workername and worker password.

## To launch the miner, use the syntax:

- ccminer -c MAXcoin-<poolname>.conf

## With thecoin.pw:

- You need to create an account and create a worker within your account.
- Address: thecoin.pw
- Port: 4100
- Replace the username and worker from your created account.
- Example of thecoin.pw config file:

- {
“algo” : “keccak”,
“url” : “stratum+tcp://thecoin.pw:4100”,
“user” : “username.workername”,
“pass” : “worker_password”
}

## With Crypto Hub:

- You need to create an account to access the pool.
- Address: cryptohub.online
- Port: 5000
- Replace the username with the email that you used to register. If you wish to specify a worker name, place the worker name after the email, starting with :
- Example of Crypto Hub config file:

- {
“algo” : “keccak”,
“url” : “stratum+tcp://cryptohub.online:5000”,
“user” : “user@email.com:worker_name”,
“pass” : “x”
}

## With zpool:

- Zpool pays in BTC, so you need to pass your BTC address as username.
- Address: keccak.mine.zpool.ca
- Port: 5133
- Example of zpool config file:
- {
“algo” : “keccak”,
“url” : “stratum+tcp://keccak.mine.zpool.ca:5133”,
“user” : “18QDfuLJnEyHbCvioD39CkuhKZzMUDrRFS”,
“pass” : “x”
}

## With MiningPoolHub:

- You need to create an account and create a worker within your account.
- Address: hub.miningpoolhub.com
- Port: 20461
- Replace the username and worker from your created account.
- Example of MiningPoolHub config file:
- {
“algo” : “keccak”,
“url” : “stratum+tcp://hub.miningpoolhub.com:20461”,
“user” : “username.workername”,
“pass” : “worker_password”
}

- Happy mining!

## Sources
---

[GPU (Nvidia) Mining Guide](https://github.com/decentralized/GPU-nVIDIA-Maxcoin-Mining-Guide) 
