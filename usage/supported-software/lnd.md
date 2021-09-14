# LND

## lnd and lncli

### **About**

`lnd` is a feature-full implementation of Lightning Network. It can be controlled from other graphical apps like Thunder, RTL or from command line using `lncli`.

### **Usage**

* **Installing `lnd` automatically installs `lnd-unlocker`, which creates a wallet right after installation and stores the seed in `/var/lib/lnd-system-mainnet/.seed.txt`**
* The above behavior can be overridden by `--no-install-recommends`, but **do not do it unless you prefer false sense of security. Without unlocker `lnd` will stay down after crash. If long enough others may steal your sats!**
* Check `thunderhub` and `ridetheln` packages for a nice graphical interface.
* Check `lndconnect` package to connect to LND with Zap.
* You can use `sudo` to run `lncli` or add yourself to group `lnd-system-mainnet`.
* If you want to grant some user readonly or invoice access, add them to group `lnd-system-mainnet-readonly` or `lnd-system-mainnet-invoice`
* A special package `lnd-genmacaroon` takes care of generating a special macaroon that is a union of readonly and invoice. It's stored at `/var/lib/lnd-system-mainnet/invoice/invoice+readonly.macaroon`. This is currently used by BTCPayServer.

#### Accessing LND

In order to conveniently access `lnd`, `lncli` is wrapped in a script called `xlncli`. This is set as the default using great Alternatives system. If you dislike `xlncli` for any reason, you can easily configure `lncli` command to use real `lncli`. However, this should not be needed since `xlncli` passes all arguments to `lncli` as needed. It only inserts additional arguments telling `lncli` to connect to the local `lnd` if it doesn't detect that you're attempting to connect to some other daemon. In other words, running something like `lncli getinfo` will connect to your own server \(if you have permissions - read below\), while `lncli --rpcserver somethingelse --macaroonpath somethingelse/admin.macaroon --tlscertpath somethingelse/tls.cert getinfo` will connect to a server `somethingelse` using given credentials.

In order for this to work, the user running `lncli` must have the permission to read macaroons. The easiest way to do that is run it with `sudo`, which causes `xlncli` to automatically identify admin permissions and use `admin.macaroon`. Giving another user \(including yourself\) the access to admin macaroon is as simple as running `sudo usermod -a -G lnd-system-mainnet username`. For invoice macaroon, use `sudo usermod -a -G lnd-system-mainnet-invoice username`, finally `sudo usermod -a -G lnd-system-mainnet-readonly username` will give `username` read-only access to LND.

