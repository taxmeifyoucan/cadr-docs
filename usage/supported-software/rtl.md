# RTL

## ridetheln

### **About**

RTL \(Ride The Lightning\) is a multi-node Lightning web UI.

### **Usage**

* The esiest way of accessing RTL is from selfhost-dashboard
* Run `sudo /usr/share/selfhost/lib/get_default_domain.sh && echo -n '/rtl/?access-key=' && sudo cat /var/lib/ridetheln-system/sso/cookie` to get the ddirect link to RTL.
* Both mainnet and regtest LND use the same RTL!
* Integrated with `selfhost` - please read the docs of `selfhost`.

#### Accessing RTL 

Accessing RTL is pretty much the same as accessing BTCPayServer. Same rules about `selfhost-*` packages. Go read that docs first.

It's impossible to change the web path to something else than `/rtl`. It's because it's hard-coded and can't be "un-hard-coded" because of some limitation of JavaScript/NodeJs/NPM or whatever crap, if I understand it correctly. Sorry.

