# BTCPay server

## btcpayserver

### **About**

BTCPayServer is a self-hosted server compatible with Bitpay API.

### **Usage**

* When you install `btcpayserver` it automatically installs tooling to get onion domain
* You can get the host name using `sudo /usr/share/selfhost/lib/get_default_domain.sh && echo`
* **You must access `http://....onion/btcpay` right after installation and register an admin account!**
* Integrated with `selfhost` - please read the docs of `selfhost`.

### Notable differences from the Docker deployment:

* No shitcoins \(not that I'd hate them, I just don't have the time for them\)
* Lightning setup is more secure \(uses a specialized macaroon to prevent BTCPayServer from spending money\)
* LND seed is not exposed to BTCPayServer, thus not visible in the UI.
* Lower attack surface \(Docker not needed\)
* "External services" not provided via BTCPayServer UI for security reasons. There will be a specialized UI for securely handling installed services.
* Some questionable packages are not available now \(kitchen-sink like pihole\)
* Some useful packages not packaged yet.

#### Accessing BTCPayServer

There are two ways to access BTCPayServer: over Tor hidden service \(`.onion` domain\) and over "clearnet" - using regular domain. The former is much easier and more secure for general users, but more difficult to access for their customers. `onion` is picked by default since it doesn't require any additional input. If you wish to use clearnet domain, you must install `selfhost-clearnet` package, which will ask you about the domain name during config phase using `debconf`. Unless you use `--no-install-recommends`, it will also install `selfhost-clearnet-certbot`, which asks for an e-mail address and creates a TLS certificate for you using Letsencrypt. If you use clearnet domain during initial installation, onion is skipped by default. You must specify it explicitly if you want both.

Once you have the appropriate packages installed, go to `http(s)://domain/btcpay` \(unless you adjusted the path during debconf phase\). You can get the onion domain by running `sudo cat /var/lib/tor/selfhost_hidden_service/hostname`. BTCPayServer will ask you to register an admin account. Thus, it's recommended to visit the domain and register the account ASAP. You can then continue using BTCPayServer as you normally would. You might find some features missing, that are present in the docker version. These features are being worked on \(except for shitcoins; not that I'd hate them too much, I just don't have time for them, when there are more important things to address\). You can affect the priority by letting me know which features do you need the most.

