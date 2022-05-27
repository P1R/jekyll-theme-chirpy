---
title: Maxcoin IPFS nodes
author: p1r0
date: 2022-05-19 19:00:00 +0600
categories: [Developers, Services]
tags: [Developers, Services]
---

The Maxcoin project in its efforts to decentralize as much as possible its ecosystem, now is working on having ipfs nodes which can host multiple services like our web3 website, decentralized blockchain bootstrap backups, and other functions that might come in the future. The following guide is on how to setup an IPFS node for Maxcoin Requirements if you want to contribute and provide some infrastructure for the current and future projects. This guide is based  on Debian 11 and Ubuntu 18.04, improvements to the current manual are always welcome.

## IPFS Instalation [<sup>1</sup>](https://docs.ipfs.io/install/command-line/#official-distributions)

1. Download the Linux binary from [`dist.ipfs.io`](https://dist.ipfs.io/#go-ipfs).

   ```bash
   wget https://dist.ipfs.io/go-ipfs/v0.12.2/go-ipfs_v0.12.2_linux-amd64.tar.gz
   ```

1. Unzip the file:

   ```bash
   tar -xvzf go-ipfs_v0.12.2_linux-amd64.tar.gz

   > x go-ipfs/install.sh
   > x go-ipfs/ipfs
   > x go-ipfs/LICENSE
   > x go-ipfs/LICENSE-APACHE
   > x go-ipfs/LICENSE-MIT
   > x go-ipfs/README.md
   ```

1. Move into the `go-ipfs` folder and run the install script:

   ```bash
   cd go-ipfs
   sudo bash install.sh

   > Moved ./ipfs to /usr/local/bin
   ```

1. Test that IPFS has installed correctly:

   ```bash
   ipfs --version

   > ipfs version 0.12.0
   ```

## Setup ipfs service for maxcoin

First time config setup for a server:
   ```sh
      ipfs init --profile server
   ```
> This removes local discovery requests

### Setup Circuit Relay V2
Add swarm address in the config (specifically the ws line):
   ```sh
       ipfs init —- profile server"Swarm": [
         "/ip4/0.0.0.0/tcp/4001",
         "/ip4/0.0.0.0/tcp/4004/ws",
         "/ip6/::/tcp/4001",
         "/ip4/0.0.0.0/udp/4001/quic",
         "/ip6/::/udp/4001/quic"
       ]
   ```

Enable Swarm.RelayService with the following command:
   ```sh
      ipfs config --json Swarm.RelayService.Enabled true
   ```

Enable Swarm.AutoRelay also with the following command:
   ```sh
      ipfs config --json Swarm.EnableAutoRelay true
   ```
and

   ```sh
      ipfs config --json Swarm.RelayClient.Enabled true
   ```

### Maxcoin special configs 
Change the gateway port from 8080 to 8081 (since the maxcoind uses 8080 for the rpc)
Edit ~/.ipfs/config and change the folling line in the Addresses section:
   ```sh
       "Gateway": "/ip4/0.0.0.0/tcp/8081",
   ```

## Set IPFS as a daemon and Nginx Reverse Proxy
### Set IPFS as a daemon

Copy the following lines after the `sudo vim... command`, modify user and path to ipfs so that it matches with your system and user that runs ipfs: 

   ```sh
    $ sudo vim /etc/systemd/system/ipfs.service
   
   [Unit]
   Description=IPFS Daemon
   
   [Service]
   ExecStart=/usr/local/bin/ipfs daemon --enable-pubsub-experiment
   User=nodemaster
   Restart=always
   LimitNOFILE=10240
   
   [Install]
   WantedBy=multi-user.target
   ```

   **NOTE: in this example user that runs ipfs is nodemaster, also the ipfs location is at /usr/local/bin/ipfs if you don't know the path, try `$ whereis ipfs`**

Enable the service

   ```sh
    $ sudo systemctl daemon-reload
    $ sudo systemctl enable ipfs.service
    $ sudo systemctl start ipfs.service
    $ sudo systemctl status ipfs.service
   ```
   **NOTE: service must be set as active (running), if not please verify the preview steps**

### Nginx Reverse Proxy for a public gateway and websocket 

The Gateway setup:
Change the server name for your own domain name:
   ```sh
   server {
       listen 80; 
       server_name gateway.maxcoinproject.net;

       location / {
           proxy_pass http://localhost:8081;
           proxy_set_header Host $host;
           proxy_cache_bypass $http_upgrade;
           allow all;
       }
   }
   ```
> Note: Remember to enable the service and get ssl with certbot

Enable Secure WebSocket with nginx

   ```sh
   server {
       listen 80; 
       server_name ipfsnode.maxcoinproject.net;

       location / {
           proxy_pass http://127.0.0.1:4004;
           proxy_http_version 1.1;
           proxy_set_header Upgrade $http_upgrade;
           proxy_set_header Connection "upgrade";
       }
   }
   ```

> Note: Remember to enable the service and get ssl with certbot

## Testing

### Verify Secure WebSocket connection
Doing an IPFS ping
   ```sh
   maxcoin@MAXCOIN01:~/.ipfs$ ipfs ping /dns4/ipfsnode2.maxcoinproject.net/tcp/443/wss/p2p/12D3KooWEEtWg9ferUVENWeomJHaURHJ6e1UzHAKYiESaSeVGv6v
   PING 12D3KooWEEtWg9ferUVENWeomJHaURHJ6e1UzHAKYiESaSeVGv6v.
   Pong received: time=161.27 ms
   Pong received: time=161.13 ms
   Pong received: time=161.55 ms
   ```
Doing a swarm connect
   ```sh
   maxcoin@MAXCOIN01:~/.ipfs$ ipfs swarm connect /dns4/ipfsnode2.maxcoinproject.net/tcp/443/wss/p2p/12D3KooWEEtWg9ferUVENWeomJHaURHJ6e1UzHAKYiESaSeVGv6v
   connect 12D3KooWEEtWg9ferUVENWeomJHaURHJ6e1UzHAKYiESaSeVGv6v success
   ```

### check the IPFS public Gateway:

Browse by adding `/ipns/ipfs.io/` to your gateway address:
> You should see the IPFS official web3 website

Example:
https://gateway.maxcoinproject.net/ipns/ipfs.io/

## License

[**UNLICENSE**](./LICENSE). ?

## Contact.

***Developers***
- [David Serrano](https://twitter.com/getmaxcoin)
- [p1r0](mailto:p1r0@nethunters.xyz)

## ToDo/Proposal

* Setup a Maxcoin testnodes health by forking [this code](https://github.com/ipfs/public-gateway-checker)
* Setup and handle data with [ipfs-cluster](https://cluster.ipfs.io/)


## References

1. [Install IPFS CLI](https://docs.ipfs.io/install/command-line/#system-requirements)
2. [file transfer](https://github.com/ipfs/go-ipfs/blob/master/docs/file-transfer.md)
3. [circuit relay](https://docs.libp2p.io/concepts/circuit-relay/)
4. [understanding circuit relay](https://blog.aira.life/understanding-ipfs-circuit-relay-ccc7d2a39
)
5. [experimental features](https://github.com/ipfs/go-ipfs/blob/master/docs/experimental-features.md)

