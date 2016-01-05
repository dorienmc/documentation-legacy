
---
## Run your own client
The formide-client, a node.js package that connects your 3D printers to the FORMIDE cloud platform can be installed on custom devices. We support Raspberry Pi 2, Beagle Bone Black and Mac (Intel x64). If you'd like support for another type of device, please contact us and ask if it's in the pipeline or not (or contribute to GitHub to support it!).

> Warning: this guide is intended for people that know how Raspberry Pi (or similar devices) work(s) and have linux
knowledge to some extend. We do not provide support for users running their own client outside of filing issues on GitHub.
To make your client work with the cloud platform, you need a subscription and a whitelisted MAC address. If you're not sure
how all of this works, you can just buy The Element and enjoy an easy setup and print within minutes!

---
### Step 1: Setup your device
First, you need to setup your device to run all needed services correctly. This includes a working operating system (recent versions of Raspbian or Debian distributions should work), an internet connection (Raspberry Pi supports USB WiFi dongles) and Git.

---
### Step 2: Install node.js and NPM
Installing node.js and NPM differs per device and user settings. Node.js has excellent documentation on how to install on your device available at their website. Be sure to install the **latest LTS release** of node.js (4.2) and the NPM version that comes with it.

---
### Step 3: Install formide-client
To install the client software, you only have to run 1 command:

```
npm install -g formide-client
```

This will install the client, binaries for drivers and Katana and all needed dependencies. Be sure to keep an eye on the installation procedure to make sure your system is compatible (warning will occur when no compatible binaries are found for native dependencies).

---
### Step 4: Subscribe your MAC address
To get cloud access with your device, you have to subscribe to FORMIDE and whitelist your MAC address. This way, we know who is
connecting to our services and that the connection can be trusted. It also allows us to ban users that are doing things with our
API that they shouldn't be doing ;).

---
### Step 5: Setup and print!
After all that's set up, simply go to FORMIDE.com, login, go to settings -> devices and register a new (custom) device using the setup flow. After completing the setup, you can plug a printer into your device and start printing!
