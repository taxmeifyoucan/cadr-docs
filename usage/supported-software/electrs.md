# Electrs

## electrs

### A**bout**

An efficient re-implementation of Electrum server in Rust. A perfect choice for user-friendly personal use.

### **Usage**

* ~~`electrum-trustless-mainnet` depends on it, so if you install it on desktop, it should work~~ Dependency is currently broken and intentionally left broken until remote access is implemented.
* `/etc/electrs-mainnet/conf.d/interface.toml` contains all information required for accessing `electrs`, but you probably only need port.
* If you want to use `electrs` remotely you need some kind of tunnel - so far manual only, look at the port above

