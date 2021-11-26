---
title: HOWTO Maxcoin Wallet with virtualbox 
author: p1r0
date: 2021-11-21 16:41:00 +0800
categories: [Developers, Wallets]
tags: [HOWTOs, Wallets, Developers, Tools]
render_with_liquid: false
---

This is a HOW TO build and run "The Maxcoin Core Wallet" with VirtualBox

## Requirements

* [VirtualBox](https://www.virtualbox.org/) 
* [7Zip](https://www.7-zip.org/) or some other program to un7zip
* [Ubuntu 18.04.3 VDI](https://www.osboxes.org/ubuntu/) 
  - VirtualBox (VDI) 64bit  Size: 1.5GB approx.


## Install and Setup the environment

1. Download and install [7Zip](https://www.7-zip.org/) or already have a software that can un7zip 7zip files.
2. Download [VirtualBox](https://www.virtualbox.org/) from https://www.virtualbox.org/wiki/Downloads and get the one that fits your Operative System.
3. Download the [Ubuntu 18.04.3 VDI](https://www.osboxes.org/ubuntu/) (this is the virtualbox image)
4. Install virtualbox following one of the manuals
   * For windows follow the [Part 1 only](https://www.wikihow.com/Install-VirtualBox)
   * For MacOS follow the [Part 2 only](https://www.wikihow.com/Install-VirtualBox)
   * For Linux follow the [Part 3 only](https://www.wikihow.com/Install-VirtualBox)
6. un7zip the downloaded VDI 7zip file
7. Follow the osboxes guide to setup the extracted image https://www.osboxes.org/guide/ at the VirtualBox Section

## Setup/Mount a folder to share between guest and host.

To setup a shared folder between guest and host use [*this guide*](https://helpdeskgeek.com/virtualization/virtualbox-share-folder-host-guest/)

> **NOTE:**
> The guest folder is used for dev and git updates.
>The host folder is used to compile and run source code in the guest folder.


***
## License

[**UNLICENSE**](./LICENSE).

## Contact.

***Developers***
- [David Serrano](https://twitter.com/getmaxcoin)
- [p1r0](mailto:p1r0@nethunters.xyz)

## ToDo/Proposals

 - Use a smaller VirtualBox Image (to reduce resources and increase speed)
     - ubuntu server lts
     - lubuntu
 - Integrate the linked manuals to the main howto and use them as references instead
 - Check license for documentation

## Links & References
1. [Document Source](https://github.com/Max-Coin/virtualbox-dev-environment)

