---
description: Following pages will guide you through using each included software.
---

# Supported software

## Operating system

Only[ Debian 10 \(Buster\)](https://www.debian.org/distrib/netinst) is currently tested and officially supported. All distributions based on it \(Ubuntu, Mint...\) should work as well. If you try it, [please report](../../community/support-1.md) your experience to us. 

## Applications

Supported applications in the repository include the most important stack to use Bitcoin full node with Lightning Network Daemon. Apps for managing software with UI are one click away on Selfhost Dashboard, this includes Thunderhub, Ride The Lightning, BTCPayServer, BTC RPC Explorer, BTC Transmuter. 

{% hint style="info" %}
Selfhost Dashboard can be installed as `apt install selfhost-dashboard` and is reachable on your server under `/dashboard`. 
{% endhint %}

![Selfhost Dashboard](../../.gitbook/assets/image%20%283%29.png)

> Nextcloud and similar apps for selfhosting services might be added in the future.

Other software and management tools are currently not accessible via UI but can be easily handled using terminal. 

### Installing applications

After you successfully [added repository to your list of sources](../setup.md#how-to-setup-the-beta-debian-repository) and updated information about packages, installing apps comes down to simple `apt install`. Keep in mind to install just desired applications and don't care about their dependencies. 

For example, if you want to use Lightning with UI, you can run only:

```text
apt install thunderhub ridetheln 
```

Which will install bitcoind, lnd, tor with all their dependencies and then Thunderhub and RTL, everything automatically connected with correct configuration. 

{% hint style="info" %}
Apps are by default accessible via tor onion service. Hostname can be found in `/var/lib/tor/selfhost_hidden_service/hostname` 
{% endhint %}

  
Let's look how to install all applications and features in **one command**:

```text
apt install selfhost-dashboard thunderhub ridetheln btcpayserver transmuter electrs btc-rpc-explorer 
```

Installing everything you need with one command like this makes sure all configuration is satisfied and doesn't have to change in the future \(maybe trigger Bitcoin resync\). Plus now you are ready to use full power of all Bitcoin weapons without ****further hesitation. 

### Updating

Packages are regularly updated with newest releases, new features and fixes. Updating whole stack is as easy as any other software:

```text
sudo apt update
sudo apt dist-upgrade
```

For information how to use individual apps, proceed to following pages. 

### Overview of currently supported and planned application packages

* [x] bitcoind
* [x] bitcoin-mainnet
* [x] bitcoin-pruned-mainnet \(provides bitcoin-chain-mode-mainnet\) DO NOT DEPEND ON THIS ONE!!!
* [x] bitcoin-fullchain-mainnet \(provides bitcoin-chain-mode-mainnet\)
* [x] bitcoin-txindex-mainnet \(provides bitcoin-chain-mode-mainnet\)
* [x] bitcoin-chain-mode-mainnet makes sure to consistently select pruned/non-pruned/txindex
* [x] bitcoin-zmq-mainnet
* [x] bitcoin-cli \(with a wrapper that uses bitcoin-mainnet by default\)
* [ ] bitcoin-p2p-mainnet \(virtual, Bitcoin P2P protocol\)
* [x] bitcoin-rpc-proxy
* [x] bitcoin-rpc-proxy-mainnet
* [x] bitcoin-timechain-mainnet \(public timechain RPC calls\)
* [x] electrs
* [x] electrs-mainnet
* [ ] electrs-esplora
* [ ] electrs-esplora-mainnet
* [ ] esplora
* [ ] esplora-mainnet
* [ ] electrumx \(low priority\)
* [ ] electrumx-mainnet \(low priority\)
* [ ] electrum-server-mainnet \(virtual, electrum server implementation\)
* [x] electrum \(desktop package without .desktop file\)
* [x] electrum-trustless-mainnet \(desktop package configured to use electrum-server-mainnet\)
* [ ] wasabi-trustless-mainnet
* [ ] wasabi \(desktop package without .desktop file\)
* [x] nbxplorer
* [x] nbxplorer-mainnet \(no integration into nginx yet\)
* [x] btcpayserver
* [x] btcpayserver-system-mainnet
* [x] btcpayserver-lnp-system-mainnet \(connects LND with BTCPayServer\)
* [x] btc-transmuter
* [x] btc-transmuter-system-mainnet
* [x] selfhost \(a tooling/framework for selfhosting applications easily\)
* [x] selfhost-nginx \(nginx gateway for selfhost\)
* [x] selfhost-clearnet \(sets up clearnet domain\)
* [x] selfhost-clearnet-certbot \(automatically sets up Let's Encrypt for selfhost-clearnet\)
* [x] selfhost-onion \(automatically sets up onion address for selfhost\)
* [x] lnd
* [x] lnd-system-mainnet
* [x] lnd-auto-unlock
* [x] lnd-unlocker-system-mainnet
* [x] lnd-genmacaroon \(generates additional macaroons - currently only invoice+readonly for use with btcpay\)
* [x] lnd-genmacaroon-mainnet
* [x] lncli \(with a wrapper that uses lnd-system-mainnet by default\)
* [x] lndconnect a CLI tool for creating lndconnect link
* [ ] eclair
* [ ] eclair-system-mainnet
* [ ] eclair-turbo
* [ ] eclair-turbo-system-mainnet
* [ ] eclair-rpc-proxy
* [ ] eclair-rpc-proxy-mainnet
* [ ] eclair-invoice-mainnet \(virtual, I guess\)
* [ ] ln-system-mainnet \(virtual, provides system-wide Lightning Network implementation\)
* [x] ridetheln
* [x] ridetheln-system
* [x] ridetheln-lnd-system-mainnet
* [x] thunderhub
* [x] thunderhub-system-mainnet
* [x] btc-rpc-explorer
* [x] btc-rpc-explorer-mainnet
* [ ] lighter
* [ ] multiuser-ln \(completely new application allowing multiple users to share a LN implementation\)
* [ ] multiuser-ln-mainnet
* [ ] liblightning \(a completely new library abstracting away implementation details and allowing multiple wallets\) - maybe just use lighter instead
* [ ] ln-contacts \(a completely new application providing contact list for Lightning Network nodes\)
* [ ] ln-dialog \(partialy done in qpay, a simple dialog which shows whenever the user attempts to pay, create invoice or open LNURL\)
* [ ] qpay-rpc-service
* [ ] qpay-client
* [ ] ln-mime \(makes sure to register appropriate mime types and launch correct application\)
* [ ] remote-service-bridge \(a framework for securely bridging services to remote computers, needs to be written\)
* [ ] samourai-dojo
* [ ] samourai-dojo-mainnet
* [ ] joinmarket
* [ ] joinmarket-mainnet
* [x] lnpbp-testkit \(framework for testing LNP/BP applications\)
* [x] remir \(a simple server for controlling IR devices; not freedom related, but why not?\)
* [ ] translations
* [x] all services for regtest
* [ ] all services for signet
* [ ] all services for testnet

