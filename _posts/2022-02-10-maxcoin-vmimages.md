---
title: Maxcoin VM images
author: p1r0
date: 2022-02-11 03:00:00 +0600
categories: [Developers, Tools]
tags: [Developers, Projects, ToDo]
---

Currently we have three images supporting virtualbox, vmware and kvm. They come with precompiled maxcoin wallet, the images just require you to setup the maxcoin.conf file, setup your password, and you are ready to sync!


## 1. Download the image for your preferred virtualization software.


* [KVM image](https://link.ap1.storjshare.io/jxwowj237xhb42zwd2oonztln2ia/p1r0backups%2Fmaxcoin.qcow2.tar.xz?download=1)
* [VirtualBox image](https://link.ap1.storjshare.io/jxaflvlz5jtl3esw4lck235zrs4a/p1r0backups%2Fmaxcoin.vdi.tar.xz?download=1)
* [VMWARE image](https://link.ap1.storjshare.io/jvz53btg4sujejv46bqpd6vg22sq/p1r0backups%2Fmaxcoin.vmdk.tar.xz?download=1)

> **NOTE:** Once downloaded, you must verify the images integrity which should match the sha256 checksum hash compare it with the [checksums-images.txt](https://link.ap1.storjshare.io/jxmk4st64znhgdptsng6scxn3wfa/p1r0backups%2Fchecksums-images.txt?download=1).

## Login Info



| Username | Password | 
| -------- | -------- |
| maxcoin  | maxcoin  |

> **NOTE:** the maxcoin user is sudoer


## Install and Setup the virtual machine for VirtualBox

1. Download and install [7Zip](https://www.7-zip.org/) or already have a software that can un7zip 7zip files.
2. Download [VirtualBox](https://www.virtualbox.org/) from https://www.virtualbox.org/wiki/Downloads and get the one that fits your Operative System.
3. Download the [VirtualBox image](https://mega.nz/file/tFgRBYKB#Y3mUWb3g06f7GZwWOIpcVufh3KGGXbPCQ0pxAd09Ev0)
4. Install virtualbox folloing one of the manuals
   * For windows follow the [Part 1 only](https://www.wikihow.com/Install-VirtualBox)
   * For MacOS follow the [Part 2 only](https://www.wikihow.com/Install-VirtualBox)
   * For Linux follow the [Part 3 only](https://www.wikihow.com/Install-VirtualBox)
6. un7zip the downloaded VDI tar.xz file
7. Follow the osboxes guide to setup the extracted image https://www.osboxes.org/guide/ at the VirtualBox Section

### Setup/Mount a folder to share between guest and host.

To setup a shared folder betwwn guest and host use [*this guide*](https://helpdeskgeek.com/virtualization/virtualbox-share-folder-host-guest/)

> **NOTE:**
> The guest folder is used for dev and git updates.
> The host folder is used to compile and run source code in guest folder.
> REMEMBER TO UPDATE THE `maxcoin.conf` file and update your PASSWORD.


---


## Install and Setup the virtual machine for KVM (GNU/Linux)

1. Download the [KVM image](https://mega.nz/file/IAwFmA7a#mX0FeSGAdCJ-0LQ-iGoKQWESo6qKo3UqCqNGwOHGwrk).
2. Decompress the [tar.xz image](https://computingforgeeks.com/how-to-extract-xz-files-on-linux/).
4. Install kvm with qemu support by following one of this manuals
   * [Ubuntu Guide](https://help.ubuntu.com/community/KVM/Installation)
   * [Debian Guide](https://computingforgeeks.com/how-to-install-kvm-virtualization-on-debian/)
   * [Centos KVM](https://phoenixnap.com/kb/install-kvm-centos)
   * [Arch Guide](https://computingforgeeks.com/install-kvm-qemu-virt-manager-arch-manjar/)
6. Import the qcow2 image from qemu, following [this guide](https://ostechnix.com/create-a-kvm-virtual-machine-using-qcow2-image-in-linux/) from  the `2. Import Qcow2 images using Virt-manager`section.

---

## Latest Blockchain automatic backups. (approx. 10 hours to sync)

In case your blockchain sync is going too slow, we have a temporal solution that is downloading the latest blockchain
copy, Please refer to [MIP2](/posts/MIP2-informational/) if you want to help us distribute it in a better way

1. Download the latest [MaxCoin BlockChain](https://mega.nz/file/gZ5DxTiS#CplvVymfIP8NJUfWW0zFD23UwoePWXeuFhKfjjwHlV4)
2. Verify the hash corresponds to `6d73ef55cc7f1964bea3da875cb0aff1a992ffd9325dd81c2645fd290c20db38`
Execute the following command to the downloaded file:

```sh
$sha256sum maxcoinBlockChainBack-1651801511.tar.xz 
6d73ef55cc7f1964bea3da875cb0aff1a992ffd9325dd81c2645fd290c20db38  maxcoinBlockChainBack-1651801511.tar.xz
``` 
> Note: if the hash is diferent from this one, do not follow up and contact us at the [telegram channel](https://t.me/maxcoinproject)

3. move the file to your home directory and extract the file
```sh
$cd ~ && tar xvf maxcoinBlockChainBack-1651801511.tar.xz  
```
4. execute the maxcoin-qt wallet
```sh
$cd ~/maxcoin && ./maxcoin-qt  
```

## License

[**UNLICENSE**](./LICENSE). ?

## Contact.

***Developers***
- [David Serrano](https://twitter.com/getmaxcoin)
- [p1r0](mailto:p1r0@nethunters.xyz)

## ToDo/Proposal

 - Integrate dnsseed script and precopiled.
 - Integrate the linked manuals to the main howto and use them as references instead.
 - Check license for documentation.

