---
description: >-
  This section explains specifics of various applications packaged in the
  repository.
---

# Bitcoin

## bitcoind and bitcoin-cli

### **About**

`bitcoind` is the full node implementation, the heart of Bitcoin ecosystem. `bitcoin-cli` package/command can be used to control `bitcoind` from command line. 

### Usage

**Important: unless you \(directly or indirectly\) install bitcoin-fullchain-$network or bitcoin-txindex-$network the node will be pruned by default. Some packages \(electrs, lnd, ...\) depend on fullchain, so they won't break. To avoid waiting for reindex, do NOT install the packages one-by-one - install all desired packages using a single `apt install` command.**

### Changing Bitcoind data directory and other settings

Default data directory including chain data is in `/var/lib/`like any other application. You can choose own datadir and other configuration like pruning size, dbcache, ports, etc, either **before installation** or **change it afterwards**. 

#### Choosing config before the installation

Before installing, environment variable which defines debconf priority has to be set. Using `sudo`, installation prompting configuration can be easily done with one command:

```text
sudo DEBIAN_PRIORITY=medium apt install bitcoin-mainnet
```

This will prompt you to choose various configuration options including Bitcoin datadir. You can leave default settings if you are not sure about other options. 

#### Changing config when Bitcoind is installed

Configuration can be changed using  `dpkg-reconfigure` as any other software. But in case of changing Bitcoin directory, you might also want to move existing data to the new directory.   
Example for `bitcoin-mainnet`package:

```text
# Bitcoind is automatically running after the installation. First, stop bitcoind service: 
sudo systemctl stop bitcoin-mainnet
# Move relevant files:
sudo mv /var/lib/bitcoin-mainnet /new-volume/bitcoin-mainnet
# Now you can choose the new directory:
sudo dpkg-reconfigure bitcoin-mainnet
# Service should auto-start, check if everything runs correctly:
systemctl status bitcoin-mainnet
```

#### User interface

Install `btc-rpc-explorer` package for a nice graphical interface.

#### `bitcoin-cli`

* You need `sudo` to run `bitcoin-cli`, group support not implemented yet, PRs welcomed.
* `bitcoin-cli` is not actual binary, it forwards your commands to the real binary in order to work out of the box
* If `bitcoin-cli` detects that you don't have the permission for _full_ access to `bitcoind` it will use public:public if you have `bitcoin-timechain-$network` installed.
* `bitcoin-tx` is not packaged yet because I'm not sure into which package it should go
* Use `bitcoin-cli -chain=regtest` for regtest \(assuming `bitcoin-regtest` is installed\).

