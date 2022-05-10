---
title: MIP3 - SSL Update Fix
author: p1r0
date: 2022-05-04 10:15:00 +0800
categories: [MIPs, Core]
tags: [MIPs, Core]
render_with_liquid: false
pin: false
---

MIP | 3 |
title | SSL Update Fix |
description | A well known issue with libssl that requires to be fixed | 
author | p1r0 (@P1R) | 
discussion-to | https://github.com/orgs/Max-Coin/teams/maxcoin-community-devs | 
status | Draft |
type | Security | 
created | 2022-05-03 | 
requires (optional) | MIP number(s) |

## Abstract 

This is a well known issue when the libssl got updated and most of the Linux distributions did update with it
Multiple solutions came across different blockchains, since we are based on bitcoin and blakecoin we might as well do some of this updates


## MIP Workflow 

1. Research
2. Setup test enviorment
3. Fix
4. Build and Test
5. Release

## Comments 

#### Follow up how LiteCoin solved this issue. - p1r0
#### Look for the issue displayed by github - p1r0
[Security] RSA signature validation vulnerability on maleable encoded message in jsrsasign
https://github.com/advisories/GHSA-27fj-mc8w-j9wg/dependabot?query=user:Max-Coin

## References

* https://github.com/BlueDragon747/Blakecoin/commit/07eb893ca4f63f1fa787b9256e1d29368c2af3bc
* https://github.com/BlueDragon747/Blakecoin/commit/d8c747357cd6deb1b7e3d37e06441b5615e97e02
* https://github.com/peercoin/peercoin/commit/5b09830e5de0f5105534e69dbf4acffb3255869b
* https://github.com/bitcoin/bitcoin/issues/7086
* https://github.com/cygnusxi/CurecoinSource/pull/48/commits/6b93af07005b90e4f6c5785c60c10c36fa52a333
* https://github.com/bitcoin/bitcoin/pull/5949
* https://github.com/bitcoin/bitcoin/pull/6954

