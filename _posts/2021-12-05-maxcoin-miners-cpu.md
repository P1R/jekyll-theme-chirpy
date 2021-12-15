---
title: CPU Mining Guide
author: p1r0
date: 2021-12-05 15:38:00 +0800
categories: [Miners, Guides]
tags: [Maxcoin, Miners, Guides, CPUs]
render_with_liquid: false
pin: true
---

by: [https://twitter.com/mxjmpbean](https://twitter.com/mxjmpbean)

## Getting Started:

- Download cpuminer-multi v1.3.1 from [https://github.com/tpruvot/cpuminer-multi/releases](https://github.com/tpruvot/cpuminer-multi/releases) or our mining software page here.
- *note: Not Maxcoin Repo
- Unpack the downloaded file
- In the unpacked directory, you will find 4 files: 3 exe and 1 bat.
- Edit the file RUN-TimeTravel.bat to accommodate your hardware and mining pool.
- Edit RUN-TimeTravel.bat Syntax:

```sh
cpuminer-gw64-corei7 -a keccak -o stratum+tcp://pool_address:port -u your_pool_username.your_miner -p x
```

## With MiningPoolHub:

- Address: hub.miningpoolhub.com
- Port: 12003
- Replace the username and worker from your created account. Example:
```sh
cpuminer-gw64-corei7 -a keccak -o stratum+tcp://hub.miningpoolhub.com:12003 -u user.worker -p x
```
- Save and run .bat file.
 
## With Mineblocks:

- Address: stratum.mineblocks.co.uk
- Port: 3027, Diff: 0.1
- Port: 3028, Diff: 32
- Replace the username with your wallet address.
- Example:
```sh
cpuminer-gw64-corei7 -a keccak -o stratum+tcp://stratum.mineblocks.co.uk:3027 -u mSpcDussPDMPSZAE5NzNLmerwdiDDiZ9nq -p x
```
- Save and run .bat file.

## Special Notes:

- Most modern CPUs will use cpuminer-gw64-corei7.exe (default in bat file)
- Just replace the pool address and port for your favorite pool:
- Happy mining!


