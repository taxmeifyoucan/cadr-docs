# LNDConnect

## lndconnect

### **About**

`lndconnect` is a helper tool to allow connecting from Zap or other compatible UI to your LND. **Important: This package is temporary and will be eventually replaced with a graphical version!**

### **Usage**

Just run `sudo lndconnect` to get the connection string.

You can create the QR code by installing `qrencode` and running `sudo lndconnect | qrencode -o lndconnect.png`

The package is currently Tor-only due to security and other technical reasons.

#### 

