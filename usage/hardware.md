---
description: Setting up the system on dedicated hardware
---

# Hardware

## Hardware requirements

Cryptoanarchy tools shouldn't just lay in censurable servers of random cloud provider. It is recommended to use own machine with physical access, ensured safety and encrypted drive.

Getting dedicated hardware for running Bitcoin software is one time investment which can withstand many years. Optimal requirements to run this repository include:

* CPU
  * x86\_64 architecture \(ARM support is experimental\) 
* RAM
  * 8GB or more
* Network
  * Bandwidth should not be limited, initial Bitcoin sync takes up to 400GB
  * Monthly can be consumed up to 20GB
  * Ethernet connection, WiFi is not recommended
* Disk
  * minimum 500GB, for long term 1TB and more is recommended 
  * Using NVMe SSD is strongly prefered 
* UPS
  * it' higly recommended to use UPS \(with USB port\) for maximum reliability and risk avoidance
  * this repository does not currently provide tools to make automated shutdown easier but it's on the wish list

{% hint style="info" %}
Generally, modest computing power should be enough. The bottleneck is usually drive speed. During initial sync, Bitcoin client performs a lot of read/write operations, therefore using SSD for chain data is strongly recommended.
{% endhint %}

### Setup on dedicated hardware

Using dedicated hardware to run this repository is the recommended approach. Separating your day to day usage and Bitcoin software minimizes potential attack vectors and enables full utilization of the machine. 

{% hint style="danger" %}
Public beta version of this repository is compiled only for x86 architecture. Support for ARM architectures on e.g. Raspberry Pi is **experimental**. If you would like to test it, be aware of risks and reach out to us for access to experimental version. 
{% endhint %}

Easy and cheap solution for dedicated server is single board computer. There are various x86 SBCs which satisfy hardware requirements. 

#### Single board computer 

The recommended SBC for setting up this repository on a dedicated machine is Odroid H2 with at least 1TB NVMe SSD and 8GB of RAM. We recommend more RAM to leave a room for future expansion. It is also recommended to use a fan - it can get very hot otherwise! The fan is very quiet even when the chain syncs - you can't hear it until your head is very close.

The newer versions of H2 have a network card which doesn't have [the driver](https://github.com/Kixunil/r8125) in Debian stable yet. This repository offers `vendor` component which has the required driver package. The recommended approach:

* Connect your phone over USB and set it to tethering
* Install Debian 10 from netinst
* `apt install gnupg`
* Add this repository with `vendor` component included, like this: `deb [signed-by=3D9E81D3CA76CDCBE768C4B4DC6B4F8E60B8CF4C] https://deb.ln-ask.me/beta buster common local vendor`
* `apt install r8125-dkms`
* Enable the network interface in `/etc/network/interfaces`
* Disconnect the phone

SBC is one of the possible solutions to dedicated hardware. If you already own a computer with enough computing power, it might be infinetly cheaper to use it instead of buying a new one. Be careful however that older computers tend do be more prone to failures - at least storage should be reasonably new. Other cheap options for running x86 version of this repo would be second hand desktop, laptop or rack server. Machine like this with upgraded RAM and new SSD could be sufficient and effective. 



