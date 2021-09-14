# BTC Transmuter

## btc-transmuter

### **About**

A self-hosted, modular IFTTT-inspired system for bitcoin services

### **Usage**

**Warning: btc-transmuter is alpha and has some issues, make sure you read usage before using it. You MUST open `/transmuter` immediately after installing and register a new user account! Then go to server settings disable registration and hit Save.**

**Unless the situation improves this package will be replaced with something better in the future.**

* The most interesting use case is sending e-mails when an invoice is paid. Go to external services and configure BTCPayServer and SMTP, then open Presets and select the appropriate link. Fill the template and save.
* Pairing with BTCPayServer is clunky - you need to enter `yourdomain.com/btcpay` and hit Save. A pairing link will appear - click it to open BTCPayServer. Select the store you want to use and confirm. Go back to Transmuter and click Save again - it should finish pairing now.
* If you use GMail as SMTP provider you will need to use application-specific password if you use 2FA or enable "less secure" applications. IMAP has to be activated either way.

