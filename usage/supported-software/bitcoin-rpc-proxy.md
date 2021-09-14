# Bitcoin-RPC-proxy

## **bitcoin-rpc-proxy**

### **About**

Protects `bitcoind` from other applications if they become compromised.

### **Usage**

* There's not much to do with it, but you can add new users by adding a file to `/etc/bitcoin-rpc-proxy-mainnet/conf.d` and then restarting \(`systemctl restart`\)
* Install `bitcoin-timechain-mainnet` to get a read-only user accessible with `public:public` credentials.

