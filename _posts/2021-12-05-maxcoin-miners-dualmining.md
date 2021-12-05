---
title: Dual ETH/MAX Guide
author: p1r0
date: 2021-12-05 16:20:00 +0800
categories: [Miners, Guides]
tags: [Maxcoin, Miners, Guides, DualMining]
render_with_liquid: false
pin: true
---

### Claymore-Dual-Mining-Guide-MAX-ETH-for-AMD-nVIDIA

by: https://twitter.com/mxjmpbean

## Getting Started:

- Download Claymore’s Dual Ethereum AMD+NVIDIA GPU Miner for Windows from https://bitcointalk.org/index.php?topic=1433925.0
- Unpack the downloaded file
- In the unpacked directory, you will find start.bat, edit the file with the following:

- setx GPU_FORCE_64BIT_PTR 0
- setx GPU_MAX_HEAP_SIZE 100
- setx GPU_USE_SYNC_OBJECTS 1
- setx GPU_MAX_ALLOC_PERCENT 100
- setx GPU_SINGLE_ALLOC_PERCENT 100
- ethdcrminer64.exe -epool ethereum_pool:port -ewal username.worker -epsw worker_password -esm 3 -dcoin keccak -dpool maxcoin_pool:port -dwal username.worker -dpsw worker_password -allpools 1

- Since you are dual mining MaxCoin and Ethereum, you need to specifiy one pool for Ethereum and one pool for MaxCoin. For this guide purposes, we are going to set examples with MaxCoin pools, so you can use any Ethereum pool you wish. Replace ethereum_pool:port, maxcoin_pool:port, username.worker and worker_password according to the pools.

## With thecoin.pw:

- You need to create an account and create a worker within your account.
- Address: thecoin.pw
- Port: 4100
- Replace the username and worker from your created account.
- Example for thecoin.pw (1 line):
- ethdcrminer64.exe -epool ethereum_pool:port -ewal username.worker -epsw worker_password -esm 3 -dcoin keccak -dpool thecoin.pw:4100 -dwal username.worker -dpsw worker_password -allpools 1
- Save and run .bat file.

## With Crypto Hub:

- You need to create an account to access the pool.
- Address: cryptohub.online
- Port: 5000
- Replace the username with the email that you used to register. If you wish to specify a worker name, place the worker name after the email, starting with :
- Example for Crypto Hub (1 line):
- ethdcrminer64.exe -epool ethereum_pool:port -ewal username.worker -epsw worker_password -esm 3 -dcoin keccak -dpool cryptohub.online:5000 -dwal user@email.com:worker_name -dpsw x -allpools 1
- Save and run .bat file.

## With zpool:

- Zpool pays in BTC, so you need to pass your BTC address as username. Zpool does not care about worker password.
- Address: keccak.mine.zpool.ca
- Port: 5133
- Example for zpool (1 line):
- ethdcrminer64.exe -epool ethereum_pool:port -ewal username.worker -epsw worker_password -esm 3 -dcoin keccak -dpool keccak.mine.zpool.ca:5133 -dwal 18QDfuLJnEyHbCvioD39CkuhKZzMUDrRFS -dpsw x -allpools 1
- Save and run .bat file.

## With MiningPoolHub:

- You need to create an account and create a worker within your account. This pool supports both MaxCoin and Ethereum, so you can use the same pool for both coins.
- MAX pool: hub.miningpoolhub.com
- Port: 20461
- ETH pool: US: us-east.ethash-hub.miningpoolhub.com
- Europe: europe.ethash-hub.miningpoolhub.com
- Asia: asia.ethash-hub.miningpoolhub.com
- Port: 20535
- Replace the username and worker from your created account.
- Example for MiningPoolHub (1 line):
- ethdcrminer64.exe -epool us-east.ethash-hub.miningpoolhub.com:20535 -ewal username.worker -epsw worker_password -esm 3 -dcoin keccak -dpool hub.miningpoolhub.com:20461 -dwal username.worker -dpsw worker_password -allpools 1
- Save and run .bat file.
Here is a youtube vid of someone setting it up on youtube. https://www.youtube.com/watch?v=L613fkx8b-U&feature=emb_imp_woyt
- Happy Mining!


## Sources
---

[Dual ETH/MAX Guide](https://github.com/decentralized/Claymore-Dual-Mining-Guide-MAX-ETH-for-AMD-nVIDIA)
