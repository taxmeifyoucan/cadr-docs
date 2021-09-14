---
description: Five things to know before your first CADR setup
---

# Before you start ‼️

## 1. Do _**not**_ attempt to configure anything 

It will just work. 

## 2. Do understand that all services, e.g. `bitcoind` will run automatically **immediately after installation and after each boot**.

All software is running as a service, automatically enabled and started after the installation. 

## **3. By default, the LND wallet is created automatically after installation and the seed is stored in /var/lib/lnd-system-mainnet/.seed.txt**

For more details, check page about Using LND. 

## 4. Do _**not**_ attempt to configure anything 

It will just work. Really.

## 5. Make sure you have at least 400 GB of free space

Biggest portion of data including Bitcoin chain is stored in `/var/lib`. For using different volume, check [How to change Bitcoin directory](supported-software/bitcoin.md#changing-bitcoind-data-directory-and-other-settings). 

