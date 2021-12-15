---
title: Maxcoin ElectrumX (Light Wallets)
author: p1r0
date: 2021-11-25 19:40:00 +0800
categories: [Developers, Projects]
tags: [Developers, Wallets, Electrum]
math: true
---
## Install

**First you need to have the python base system requirements**
```
$ sudo apt-get update
$ sudo apt-get install build-essential python3 python3-dev python3-setuptools python3-pip virtualenv python3-multidict  python3-pytest libleveldb-dev
```

**set the virtual enviroment**
```sh
$ virtualenv -p python3 myenv
$ source myenv/bin/activate
```

You can install electrumx after that. For testing, it is not necessarily needed, but that way you can see if all would work well or if there is something missing.
```sh
git clone https://github.com/spesmilo/electrumx
cd electrumx
sudo python3 setup.py install
```
## Maxcoin Info

#### Maxcoin Ports

P2P / Testnet | 8668 / 18668
RPC / Testnet | 8669 / 18669

#### Genesis

0x0000002d0f86558a6e737a3a351043ee73906fe077692dfaa3c9328aaca21964

#### Features

Shape-shifting software defends against botnet hacks

#### Algos

Schnorr / secp256r1

## coins.py

First we need some info from maxcoin that is in the Maxcoin Info section, plus the following:

```sh
curl --user maxcoinrpc --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "gettxoutsetinfo", "params": []}' -H 'content-type text/plain;' http://127.0.0.1:8080
```

Output by the syncing time:

```
{
  "height": 4105438,
  "bestblock": "000000000000d98cff8824ce362c934bd97de404621ef854a32a68e2f345e780",
  "transactions": 887407,
  "txouts": 2136713,
  "bytes_serialized": 88311691,
  "hash_serialized": "2d8d1d8acc008e2b6da524f21e0e9b2b1a10f5a8d25b7b9f62f86f9d0b7b6a31",
  "total_amount": 75582558
}
```

TX_COUNT is the value "transactions", TX_COUNT_HEIGHT is "height" and TX_PER_BLOCK is the result of TX_COUNT/TX_COUNT_HEIGHT. The values don't have to match 100%, so for example use 2 for TX_PER_BLOCK even if the result is < 2.

```
887407/4105438.0
0.21615403764470442
```


## This is similar on how to add Maxcoin into the coins

```python
class Maxcoin(Coin):
    NAME = "Maxcoin"
    SHORTNAME = "MAX"
    NET = "mainnet"
    P2PKH_VERBYTE = bytes.fromhex("6E")
    P2SH_VERBYTES = [bytes.fromhex("70")]
    WIF_BYTE = bytes.fromhex("80")
    GENESIS_HASH = ('0000002d0f86558a6e737a3a351043ee73906fe077692dfaa3c9328aaca21964')
    DESERIALIZER = lib_tx.DeserializerSmartCash
    ENCODE_CHECK = partial(Base58.encode_check, hash_fn=lib_tx.DeserializerSmartCash.keccak)
    DECODE_CHECK = partial(Base58.decode_check,hash_fn=lib_tx.DeserializerSmartCash.keccak)
    HEADER_HASH = lib_tx.DeserializerSmartCash.keccak
    TX_COUNT = 869998
    TX_COUNT_HEIGHT = 3982932
    TX_PER_BLOCK = 1 # actually 0.21843154741281046
    RPC_PORT = 8669 
    
    @classmethod
    def header_hash(cls, header):
        '''Given a header return the hash.'''
        return cls.HEADER_HASH(header)
```
> Note: VERIFY THAT THE DESERIALIZER ALSO WORKS FOR MAXCOIN:
[This might be useful to search and compare with the smart cash](https://github.com/Max-Coin/maxcoin/blob/master/src/serialize.h)

## Maxcoin Test Block in ElectrumX

> [code section that generates it](https://github.com/Max-Coin/maxcoin/blob/2af840024c8e81697252c2e24c268a8ce9165b8d/src/rpcblockchain.cpp)
```
{
  "hash": "000000000000bc8fff5727a0d9e59632b07b21f72bce7950a928175e82fbd2d0",
  "size": 185,
  "height": 100000,
  "merkleroot": "823f4b30b806e57a07144148d8f586264780bfc33f3632da8648b20ac9d2f014",
  "tx": [
    "823f4b30b806e57a07144148d8f586264780bfc33f3632da8648b20ac9d2f014",
  ],
  "time": 1394729531,
  "nonce": 3303860448,
  "bits": "1b019144",
  "previousblockhash": "000000000000e84e3b6d60da9fc745eba5626a53fc79329c3fea8dd3a146287b",
  "block": "01000000010000000000000000000000000000000000000000000000000000000000000000ffffffff1303a08601065321e23b1a8b4901000112000000ffffffff010060343c020000001976a91430be99cd8e08ea2472e1dd47fae0928f71f0724688ac00000000"
}
```


### If the rpc is running in the main net you can also test the output from block 10000 by using the following command:

```sh
curl --user maxcoinrpc --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getblock", "params": ["000000000000bc8fff5727a0d9e59632b07b21f72bce7950a928175e82fbd2d0"]}' -H 'content-type: text/plain;' http://127.0.0.1:8080
```

Where the output might look like this:

```
{
  "hash": "000000000000bc8fff5727a0d9e59632b07b21f72bce7950a928175e82fbd2d0",
  "confirmations": 273264,
  "size": 185,
  "height": 100000,
  "version": 2,
  "merkleroot": "823f4b30b806e57a07144148d8f586264780bfc33f3632da8648b20ac9d2f014",
  "tx": [
    "823f4b30b806e57a07144148d8f586264780bfc33f3632da8648b20ac9d2f014"
  ],
  "time": 1394729531,
  "nonce": 3303860448,
  "bits": "1b019144",
  "difficulty": 41810.1101982,
  "previousblockhash": "000000000000e84e3b6d60da9fc745eba5626a53fc79329c3fea8dd3a146287b",
  "nextblockhash": "0000000000014db84e52aa3aa03064bc096044bb37c7191fab91fe7d61604701"
}
```
## ToDo

Search for electrum implementations of 365coin, Slothcoin or Cryptometh that are Keccak SHA-3 Based
ToDo: Check with Oliver how does the "Block" section in the example code works.

https://github.com/Max-Coin/maxcoin/blob/master/src/base58.h#L275

## Sources

1. [https://github.com/spesmilo/electrumx](https://github.com/spesmilo/electrumx)

2. [https://gist.githubusercontent.com/cipig/af7ff886ca92746c3cac55e90cfcdddd/raw/9e8e1860cd31763e822607648d2d447810dfb4dc/electrumx_addcoin.md](https://gist.githubusercontent.com/cipig/af7ff886ca92746c3cac55e90cfcdddd/raw/9e8e1860cd31763e822607648d2d447810dfb4dc/electrumx_addcoin.md)

3. [https://github.com/SmartCash/electrum-smart-server/commit/cc4b3e0b4076f2482683fd244ba048415eaa5b90](https://github.com/SmartCash/electrum-smart-server/commit/cc4b3e0b4076f2482683fd244ba048415eaa5b90)


