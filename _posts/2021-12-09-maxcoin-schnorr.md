---
title: Schnorr Signing Algorithm
author: p1r0
date: 2021-12-09 06:27:00 +0800
categories: [Features, Schnorr]
tags: [Features, Keccak, Schnorr]
render_with_liquid: false
---
Maxcoin addresses use Schnorr for signing algorithm allowing exciting developments such as “native multisig” to be used, and an upgraded cryptographic field for key generation and an increase in performance.

Maxcoin uses Secp256r1 as it’s cryptographic field to generate key pairs for addresses: A carefully-designed elliptical curve from which points are selected and used to initialise the public and private keys. 

The use of the Secp256k1 field is specifically recommended by NIST, an organisation that sets the standards for US government cryptography.

#### Digital Signature:
  * Includes “Native Multisig”
  * A future feature for Bitcoin
  * Uses Secp256r1 (NIST recommended)
  * Increased Performance
  * Increased Scalability
  * Anti-Spam Attacks
  * Interactive Signature Aggregation

Some Schnorr Resources:
1. [https://bitcoinmagazine.com/technical/scriptless-scripts-how-bitcoin-can-support-smart-contracts-without-smart-contracts](https://bitcoinmagazine.com/technical/scriptless-scripts-how-bitcoin-can-support-smart-contracts-without-smart-contracts)
2. [https://bitcoinmagazine.com/culture/the-power-of-schnorr-the-signature-algorithm-to-increase-bitcoin-s-scale-and-privacy-1460642496](https://bitcoinmagazine.com/culture/the-power-of-schnorr-the-signature-algorithm-to-increase-bitcoin-s-scale-and-privacy-1460642496)
3. [https://medium.com/scalar-capital/scriptless-scripts-25e18fd52ede](https://medium.com/scalar-capital/scriptless-scripts-25e18fd52ede) 
4. [https://medium.com/scalar-capital/schnorr-signatures-754038368b87](https://medium.com/scalar-capital/schnorr-signatures-754038368b87)
