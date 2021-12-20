---
title: Maxcoin Testnet (ToDo)
author: p1r0
date: 2021-11-25 19:30:00 +0800
categories: [Developers, Projects]
tags: [Developers, Projects, ToDo]
---
Maxcoin testnet implementation

## Maxcoin testnet known Info

#### Maxcoin Ports
P2P / Testnet
8668 / 18668

#### Genesis (log)

```
SetBestChain: new best=0000000a23e3eb42dc87b61d4015c80ffd85471d34e2c7210c7ca63b78a58612  height=0  log2_work=24.000022  tx=1  date=2014-01-22 23:41:21 progress=0.000000
2021-10-06 22:08:21 ResetSyncCheckpoint: sync-checkpoint reset to 0000000a23e3eb42dc87b61d4015c80ffd85471d34e2c7210c7ca63b78a58612
```

#### TestNet MagicNumbers

        pchMessageStart[0] = 0x0b;
        pchMessageStart[1] = 0x11;
        pchMessageStart[2] = 0xbb;
        pchMessageStart[3] = 0x07;
        
[Code lines with the Maxcoin testnet magic numbers](https://github.com/Max-Coin/maxcoin/blob/2af840024c8e81697252c2e24c268a8ce9165b8d/src/main.cpp#L2880)


## HowTo maxcoin.conf

The maxcoin.conf should have the following
```
# Run on the test network instead of the real maxcoin network.
testnet=1
rpcallowip=127.0.0.1
# Listen for RPC connections on this TCP port.
rpcport=8080
# Mining is initially enabled.
gen=1
```

### Verify connected peers
```
curl --user maxcoinrpc --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getpeerinfo", "params": []}' -H 'content-type: text/plain;' http://127.0.0.1:8080/
```
## ToDo / Future Development
### Build a Maxcoin a Testnet (Option 1).

1. Clone the maxcoin01-testnet and maxcoin02-testnet
2. Build the Testnet genesis block, also set it to run only testnet [1]
3. Verify it connects the peers also with the public dnsseed.decentralizeduser.com(must suport main and testnet)
4. Enable mining on bouth nodes
5. Enable the block explorer
6. Create a faucet site?

### Fork the bitcoin-testnet-box (Option 2)

Another way to work with maxcoin development and testing is to create a fork of the [bitcoin-testnet-box](https://github.com/freewil/bitcoin-testnet-box)


## Extra Info

It seems that teh code includes an already generated genesis block:
* [main.cpp](https://github.com/Max-Coin/maxcoin/blob/2af840024c8e81697252c2e24c268a8ce9165b8d/src/main.cpp#L2884)
* [checkpoints.cpp](https://github.com/Max-Coin/maxcoin/blob/2af840024c8e81697252c2e24c268a8ce9165b8d/src/checkpoints.cpp#L55)

> We might consider rebuild another genesis block and update this lines at the code, plus adding also the [dnsseed and/or some nodes](https://github.com/Max-Coin/maxcoin/blob/2af840024c8e81697252c2e24c268a8ce9165b8d/src/net.cpp#L1205) -p1r0

## Contact.

***Developers***
- [David Serrano](https://twitter.com/getmaxcoin)
- [p1r0](mailto:p1r0@nethunters.xyz)

## References

1. [https://bitcoin.stackexchange.com/questions/19287/how-to-fork-bitcoin-and-build-own-cryptocurrency](https://bitcoin.stackexchange.com/questions/19287/how-to-fork-bitcoin-and-build-own-cryptocurrency) 

