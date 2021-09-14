# Remir

## remir

### **About**

A simple server for controlling IR-enabled devices.

### **Usage**

Your device MUST have a LIRC-capable IR transmitter! I recommend using Raspberry Pi with `lirc_rpi` configured. Just install the package and either pick a password or let it generate a random one. The password will also be stored in /var/run/remir/password. After you've configured LIRC, open your browser using selfhost domain, followed by `remir` root path \(default is `/remir`\) followed by slash and the password.

