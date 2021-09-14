---
description: Various details about using this repository
---

# What to be aware of

{% hint style="warning" %}
There are many packages that are connected in various ways. They have proper dependency relationships declared that make sure you don't install a package without an important part. So for the most part, you can just blindly install packages. There are a few important things you need to have in mind, though!
{% endhint %}

* [Only Debian 10 is currently officially supported.](supported-software/#operating-system) Ubuntu and derivatives should work, but we can't be sure. Please report issues you find.
* Beware: as explained above, bitcoin and all related services will run automatically right after boot until you shutdown the computer!
* Some packages require bitcoin **without pruning** to be configured. And they will do it automatically. 
  * That means, if you have less than 350 GB of free space, you should be very careful about what you install! Basically, the only \(somewhat\) useful packages that you can install now are `bitcoin-rpc-proxy`, `nbxplorer`, `btcpayserver`, `selfhost*`, `tor-hs-patch-config`
  * `lnd`does not officially support pruning, therfore package with full history is needed
  * To be sure configuration is correct for all possible software and avoid potential resync in the future, you can [install all applications at with one command](supported-software/#installing-applications). 
* The data does **not** go to your home directory, but under `/var/lib` if you have partitioned your disks to have big home partition and small system partition, you will have to set a different path **using debconf** - read below and check [FAQ](../faq/general-faq.md#how-to-change-bitcoin-chain-data-directory).
* Contrary to the convention, all the configuration files are auto-generated and **must not** be edited! If you need to tune something, the best place to do that is using debconf. The second best place is filing a request for the setting on GitHub, if it isn't in debconf yet. If you can't wait for the implementation, place it into an appropriate `conf.d` directory and re-run debconf. However continue reading!
* Any change to configuration requires running `dpkg-reconfigure PACKAGENAME` `electrs` and `bitcoin-rpc-proxy` are smarter and they only need `systemctl restart`.
* Some configuration is special in being controlled by certain packages being or not being installed. The most important case is configuration of pruning/non-pruning/txindex of bitcoind. If you want to change the setting, you must install the appropriate package: `bitcoin-pruned-mainnet`, `bitcoin-fullchain-mainnet`, `bitcoin-txindex-mainnet`. Naturally, **only one of them can be installed at the same time**. Further **some other packages, like `electrs` require specific package to be installed!** Note however, that `txindex` implies `fullchain`, so having it installed is fine for `electrs` and such. Obviously, `pruned` can't be installed with `electrs`. While there are ways to hack this, just don't. You will run into a lot of trouble. The point of this repository is to \(hoepfuly\) never break.
* When you change the configuration of paths, they don't get moved automatically! This will be fixed eventually, just be careful around that for now.
* Many dependencies are specified using `Recommends`, which means installing stuff with `--no-install-recommends` will work, but won't be very useful.
* Lot of stuff here is intended for servers. While it can be used on desktop and the goal is to make it useful there eventually, it will take many months to get there.
* The server stuff is still considered advanced topic - read \(the end of\) the admin docs!
* `btcpayserver` and `ridetheln` \(a better name for RTL, AKA Ride The Lightning\) use a custom system of integration into `nginx` in order to get an onion domain, or even a clearnet domain with HTTPS certificate automatically. This is really great for user experience, but may be surprising to people who don't read the docs!
* If you want a clearnet domain, install `selfhost-clearnet` package. This will skip `clearnet-onion` unless you install both, of course. This operation can **not** be performed non-interactively, without preseting debconf!
* If you install `bitcoin-regtest`, all following packages will install regtest version \(e.g. installing `lnd` will install `lnd-system-regtest`\). If you have `bitcoin-mainnet` and `bitcoin-regtest` and would like install only one package, just install the single version you want e.g. `lnd-system-mainnet`

