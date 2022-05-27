---
title: Maxcoin Seeder
author: p1r0
date: 2022-02-10 16:00:00 +0600
categories: [Developers, Projects]
tags: [Developers, Projects, ToDo]
---

[maxcoin-seeder](https://github.com/Max-Coin/maxcoin-seeder) is a crawler for the MaxCoin network, which exposes a list
of reliable nodes via a built-in DNS server. It is a fork of bitcoin-seeder.


## FEATURES
* Regularly revisits known nodes to check their availability
* Bans nodes after enough failures, or bad behaviour
* Accepts nodes down to v0.3.19 to request new IP addresses from,
  but only reports good post-v0.3.24 nodes.
* Keeps statistics over (exponential) windows of 2 hours, 8 hours,
  1 day and 1 week, to base decisions on.
* Very low memory (a few tens of megabytes) and cpu requirements.
* Crawlers run in parallel (by default 96 threads simultaneously).

## REQUIREMENTS

* Debian based GNU/linux without systemd-resolvd (recommended Ubuntu 16.04).
* Have a public IP Address with access to the port 53
* Have a domain name and access to configure registries on it.
* build-essential 
* libboost-all-dev 
* libssl-dev

> Note: if your OS has systemd-resolvd reference to Known  the `KNOWN ISSUES` section

### Install dependencies:

```sh
$ sudo apt-get install build-essential libboost-all-dev libssl-dev
```

## COMPILING
First we get the repository maxcoin-seeder code

```sh
$ git clone https://github.com/Max-Coin/maxcoin-seeder
$ cd maxcoin-seeder
```

Compiling will require boost and ssl.  On debian systems, these are provided
by `libboost-dev` and `libssl-dev` respectively.

```sh
$ make
```

This will produce the `dnsseed` binary.

## USAGE
> Best practice is to have a maxcoin daemon with the blockchain on the same server as a public node

Assuming you want to run a dns seed on dnsseed.example.com, you will
need an authorative NS record in example.com's domain record, pointing
to for example vps.example.com:

```
$ dig -t NS dnsseed.example.com

;; ANSWER SECTION
dnsseed.example.com.   86400    IN      NS     vps.example.com.
```

On the system vps.example.com, you can now run dnsseed:

```
./dnsseed -h dnsseed.example.com -n vps.example.com
```

> If you want the DNS server to report SOA records, please provide an
e-mail address (with the @ part replaced by .) using -m.

### Usage with testnet enabled
> Best practice is to have a maxcoin daemon with the testnet blockchain on the same server as a public node

```
./dnsseed --testnet -h dnsseed.example.com -n vps.example.com
```

### Usage with tor enabled

#### Server Side
> Requirement: install tor (# apt install tor)
> if you follow this tutorial
> [How To Setup tor node](https://en.bitcoin.it/wiki/Setting_up_a_Tor_hidden_service)
> ***Remember that Maxcoin uses 8668 tcp port and 18668 for the testnet***

```
./dnsseed -o 127.0.0.1:9050 -h dnsseed.example.com -n vps.example.com
```

#### Client Side
> Requirement: install tor (# apt install tor)

First, you can just add it to the command line:

`$ maxcoind -proxy=127.0.0.1:9050 -addnode=mqrlomy4wdddohem.onion:8668 -listen -debug=tor`

Or you can add it to your maxcoin.conf file:

```
proxy=127.0.0.1:9050
addnode=mqrlomy4wdddohem.onion:8668
listen=1
debug=tor
```

The debug param tells it to print info about tor when the service comes up so you can see if anything is not working.

When you bring up the service, you should see a statement like

> **NOTE:** mqrlomy4wdddohem.onion:8668 is an official maxcoin tor dnsseed address.


## RUNNING AS NON-ROOT

Typically, you'll need root privileges to listen to port 53 (name service).

One solution is using an iptables rule (Linux only) to redirect it to
a non-privileged port:

```sh
$ iptables -t nat -A PREROUTING -p udp --dport 53 -j REDIRECT --to-port 5353
```

If properly configured, this will allow you to run dnsseed in userspace, using
the -p 5353 option.

## KNOWN ISSUES

SPECIAL INSTRUCTIONS FOR UBUNTU USERS

All Ubuntu releases starting with 16.10 (first released in October 2016) come installed with [systemd-resolved](https://www.freedesktop.org/software/systemd/man/systemd-resolved.service.html), which effectively prevents the seeder's built-in DNS server from working correctly. This is due to both applications requiring use of port 53, and systemd-resolved takes priority by default. There are a few ways to resolve this issue:

1.- Force the seeder to bind to a specific IP address by adding the following argument to the terminal cmd: `-a <ip address>`. This is the recommended solution as it doesn't require disabling of any operating system services.

Example:

```
sudo ./dnsseed -h dnsseed.example.com -n vps.example.com -a 123.231.123.231
```

2.- Disable binding of systemd-resolved to port 53 by editing the `/etc/systemd/resolved.conf` file and adding this line to the bottom of the file:

```
DNSStubListener=no
```

Save and reboot, and now systemd-resolved will no longer interfere with the seeder's DNS server.

>**NOTE:** This method is only supported by systemd 232 and newer. You can check your version of systemd with the cmd: `systemctl --version`

3.- Completely disable the systemd-resolved service with the following cmds (not recommended as it may cause undesired side-effects if you use the same server for anything other than running the seeder app):

```
sudo systemctl disable systemd-resolved
sudo systemctl stop systemd-resolved
```

### FIX KNOWN ISSUES AFTER PROCEDURE 2 OR 3

Sometimes after the procedure 2 or 3 there is an issue with the dns resolving addresses so it is recommended to follow this solution:

1.- Delete the resolv.conf file:

```sh
sudo rm -f /etc/resolv.conf
```

2.- Edit, add dns servers configs and write the file.

```sh
sudo vim /etc/resolv.conf
```
> Example config at the /etc/resolv.conf file:

```sh
nameserver 1.1.1.1
nameserver 1.0.0.1
~
```

3.- Set linux file system file attribute to cannot be modified

```sh
sudo chattr +i /etc/resolv.conf 
```

4.- Restart the network config depeding on your configuration

> Option 1:

```sh
sudo /etc/init.d/networking restart 
```

> Option 2:

```sh
sudo netplan apply
```


## ToDo
* Support Linux systems with systemd-resolvd service
* Support the new tor v3 addresses
* Add to the virtual machines images with an autoconfig script.

## CONTACT

***Developers***
- [David Serrano](https://twitter.com/getmaxcoin)
- [p1r0](mailto:p1r0@nethunters.xyz)
- [Maxcoin telegram group](https://t.me/maxcoinproject)


## REFERENCES

1. [maxcoin-seeder](https://github.com/Max-Coin/maxcoin-seeder)
2. [Litecoin Seeder README](https://github.com/pooler/litecoin-seeder/blob/master/README)
3. [Systemd issues](https://github.com/guapcrypto/DNS-Seeder/blob/main/README.md)
4. [Video seeder example setup](https://www.youtube.com/watch?v=DsaxbwwVEXk)
5. [Node tor configs for bitcoin](https://en.bitcoin.it/wiki/Setting_up_a_Tor_hidden_service)
6. [Set dns servers for ubuntu](https://linuxhint.com/set-dns-name-servers-ubuntu-linux/)
