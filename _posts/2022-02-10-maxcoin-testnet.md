---
title: Maxcoin Testnet
author: p1r0
date: 2022-02-10 17:00:00 +0600
categories: [Developers, Projects]
tags: [Developers, Projects, ToDo]
---

## Setup Maxcoin Testnet

### Building on Linux

> NOTE: These instructions have been tested and verified on Ubuntu 18.04

To install the required dependencies, run the following command from Ubuntu:

```sh
$ sudo apt update
$ sudo apt install -y git build-essential libssl1.0-dev libboost-all-dev libdb-dev libdb++-dev libminiupnpc-dev libqrencode-dev libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools qt5-default
```

Then grab the latest version of the MaxCoin source code from Github:

```sh
cd ~
git clone https://github.com/Max-Coin/MaxCoin.git
cd MaxCoin/src
```

To build the daemon, run the following command:

```sh
make -f makefile.unix
```

Optionally, debugging symbols can be removed from the binary to reduce its size. This can be done using strip:

```sh
strip maxcoind
```


## Edit maxcoin.conf

Get a copy of the  `maxcoin.conf` example:
```sh  
$ mkdir ~/.maxcoin/
$ mkdir ~/.maxcoin/testnet
$ cp ~/MaxCoin/maxcoin-EXAMPLE.conf ~/.maxcoin/testnet/maxcoin.conf
```

Edit the maxcoin.conf:
```sh  
$ nano ~/.maxcoin/maxcoin.conf
```

The maxcoin.conf should have the following:
```
# Run on the test network instead of the real maxcoin network.
testnet=1
# Use as many addnode= settings as you like to connect to specific peers.
addnode=a.seed.maxcoinproject.net:18668
addnode=b.seed.maxcoinproject.net:18668
rpcallowip=127.0.0.1
# Listen for RPC connections on this TCP port.
rpcport=8181
# Mining is initially enabled.
gen=1
```
> **NOTE:** the file in this example was stored at ~/.maxcoin/testnet/maxcoin.conf
> **NOTE2:** REMEMBER TO CHANGE THE PASSWORD AT THE MAXCOIN.CONF

### Run Maxcoin Testnet Server
```
$ cd ~/MaxCoin/src/
$ ./maxcoind -daemon --testnet
$ ./maxcoind  stop
$ ./maxcoind -daemon --testnet -conf=testnet/maxcoin.conf
```

### Verify connected peers
```
curl --user maxcoinrpc --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getpeerinfo", "params": []}' -H 'content-type: text/plain;' http://127.0.0.1:8080/
```
> **NOTE:** The required password is the one you set at the maxcoin.conf file.

## Testnet Data

### Port
TCP 18668

### Genesis (log)

```
SetBestChain: new best=0000000a23e3eb42dc87b61d4015c80ffd85471d34e2c7210c7ca63b78a58612  height=0  log2_work=24.000022  tx=1  date=2014-01-22 23:41:21 progress=0.000000
2021-10-06 22:08:21 ResetSyncCheckpoint: sync-checkpoint reset to 0000000a23e3eb42dc87b61d4015c80ffd85471d34e2c7210c7ca63b78a58612
```

### MagicNumbers

        pchMessageStart[0] = 0x0b;
        pchMessageStart[1] = 0x11;
        pchMessageStart[2] = 0xbb;
        pchMessageStart[3] = 0x07;
        
> [Code lines with the Maxcoin testnet magic numbers](https://github.com/Max-Coin/maxcoin/blob/2af840024c8e81697252c2e24c268a8ce9165b8d/src/main.cpp#L2880)

### Public Nodes

* a.seed.maxcoinproject.net:18668
* b.seed.maxcoinproject.net:18668
* dnsseed.testnet.maxcoinproject.net:18668
* dnsseed.testnet.maxcoinproject.com:18668
* dnsseed.testnet.decentralizeduser.com:18668

## ToDo / Future Development

1. Create a block explorer
2. Create a faucet site
3. Fork [bitcoin-testnet-box](https://github.com/freewil/bitcoin-testnet-box)?


## Contact.

***Developers***
- [David Serrano](https://twitter.com/getmaxcoin)
- [p1r0](mailto:p1r0@nethunters.xyz)

## References

1. [maxcoin build documentation](https://github.com/Max-Coin/maxcoin/blob/master/doc/) 


