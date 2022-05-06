---
title: MIP2 - Setup Bootstrap Sync
author: p1r0
date: 2022-05-03 20:30:00 +0800
categories: [MIPs, Core]
tags: [MIPs, Core]
render_with_liquid: false
pin: false
---

MIP | 2 |
title | Setup Bootstrap Sync |
description | include scripts for generating bootstrap.dat backups | 
author | p1r0 (@P1R) | 
discussion-to | https://github.com/orgs/Max-Coin/teams/maxcoin-community-devs | 
status | Draft |
type | Informational | 
created | 2022-05-03 | 
requires (optional) | MIP number(s) |

## Abstract 

by creating a boostrap.dat[4] image, and publish into an IPNS (pinned in multiple servers) and the usage of circuit relay we will be hable tu do nightly updates synced to one node that can be monitored, a second node can maybe work on weekly updates. There is already a tool inside the bitcoin core code for this prouposes[5], A considertion might be to clone it into the maxcoin repo if it works properly.


## MIP Workflow 

1. Create a bootstrap.dat file
2. Test if it can regenerate the blockchain faster than just a sync.
3. Use the bitcoin scripts or others to automate the process
4. Use crontab for update daily and weekly snapshots
5. Publish on a site with a sha256 hash
6. Publish automatically to an IPNS service name and add pins to multiple nodes so that they update

#### Security Considerations
The IPFS CID can be shown in the official site and github repo so that people do not download a compromised version of the maxcoin blockchain 


## Comments 

### p1r0 Created at: 06/17/2021 17:30 Updated at: 06/17/2021 17:30

The code from linearize is modified so that it can run on maxcoin.
First part ran without problems, but the second part has a memory issue (probably no enought).
gonna do some debugg, wait for my laptop blockchain to reach 100% sync (now at 75%) and retest it on my laptop with 16 ram gigs... Not set onHold

### p1r0 Created at: 06/20/2021 13:45 Updated at: 06/20/2021 13:45

fixed code since there was a bug in it...
updated this patch
https://github.com/bitcoin/bitcoin/pull/16802

#### p1r0 Created at: 06/22/2021 00:45 Updated at: 06/22/2021 00:45

Linearize gets frozen at the end (might need some debugging)... still the handmade bootstrap.dat works... but might not be the proper (cleaner) way to do it

#### p1r0 Created at: 07/08/2021 02:23 Updated at: 07/08/2021 02:23

Testing import to a windows Machine, after the import I will create another bootstrap.dat file but with the linearize app. For now just require to debug the python linearize tool on the current linux blockchain, look for logs and why it stucks on this specific block:
557d...e70e

## References

* 1 [Bitcoin Bootstrap.dat - Where to find and how to use Bootstrap.dat file](https://coinguides.org/bitcoin-bootstrap-dat-source-usage/) - 2021-06-17
* 2 [bitcoin/contrib/linearize at master · bitcoin/bitcoin · GitHub](https://github.com/bitcoin/bitcoin/tree/master/contrib/linearize) -	2021-06-14
* 3 [Creating my own bootstrap.dat? - Bitcoin Stack Exchange](https://bitcoin.stackexchange.com/questions/10381/creating-my-own-bootstrap-dat) 2021-06-14
* 4 [understanding-ipfs-circuit-relay-ccc7d2a39](https://blog.aira.life/understanding-ipfs-circuit-relay-ccc7d2a39) 	Related 	p1r0 	06/14/2021
* 5 [Fixed code since there awas a butg in it.. uipdated this patch](https://github.com/bitcoin/bitcoin/pull/16802)
