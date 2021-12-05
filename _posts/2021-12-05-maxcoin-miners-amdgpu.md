---
title: GPU (AMD) Mining Guide
author: p1r0
date: 2021-12-05 16:47:00 +0800
categories: [Miners, Guides]
tags: [Maxcoin, Miners, Guides, GPUs]
render_with_liquid: false
pin: true
---

by: https://twitter.com/mxjmpbean

## Getting Started:

- Download sgminer-gm v5.6.1 for PC
- Unpack the downloaded file
- In the unpacked directory, you will find several bat files.4 files.
- Create a new bat file called MAXCOIN-START.bat with the following:
- Create MAXCOIN-START.bat Syntax:

### Syntax:

- setx GPU_FORCE_64BIT_PTR 0
- setx GPU_MAX_HEAP_SIZE 100
- setx GPU_USE_SYNC_OBJECTS 1
- setx GPU_MAX_ALLOC_PERCENT 100
- setx GPU_SINGLE_ALLOC_PERCENT 100
- sgminer.exe –no-submit-stale -k keccak -o stratum+tcp://pool_address:port -u user.worker -p worker_password

## With thecoin.pw:

- You need to create an account and create a worker within your account.
- Address: thecoin.pw
- Port: 4100
- Replace the username and worker from your created account.
- Example of thecoin.pw (1 line):
- sgminer.exe –no-submit-stale -k keccak -o stratum+tcp://thecoin.pw:4100 -u user.worker -p worker_password
- Save and run .bat file.


## With Crypto Hub:

- You need to create an account to access the pool.
- Address: cryptohub.online
- Port: 5000
- Replace the username with the email that you used to register. If you wish to specify a worker name, place the worker name after the email, starting with :
- Example of Crypto Hub (1 line):
- sgminer.exe –no-submit-stale -k keccak -o stratum+tcp://cryptohub.online:5000 -u user@email.com:worker_name -p x
- Save and run .bat file.

## With zpool:

- Zpool pays in BTC, so you need to pass your BTC address as username. Zpool does not care about worker password.
- Address: keccak.mine.zpool.ca
- Port: 5133
- Example of zpool (1 line):
- sgminer.exe –no-submit-stale -k keccak -o stratum+tcp://keccak.mine.zpool.ca:5133 -u 18QDfuLJnEyHbCvioD39CkuhKZzMUDrRFS -p x
- Save and run .bat file.

## With MiningPoolHub:

- You need to create an account and create a worker within your account.
- Address: hub.miningpoolhub.com
- Port: 20461
- Replace the username and worker from your created account.
- Example of MiningPoolHub (1 line):
- sgminer.exe –no-submit-stale -k keccak -o stratum+tcp://hub.miningpoolhub.com:20461 -u user.worker -p worker_password
- Save and run .bat file.
- Happy mining!


## Sources
---

[GPU (AMD) Mining Guide](https://github.com/decentralized/GPU-AMD-Maxcoin-Mining-Guide
