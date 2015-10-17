---
### Install node.js and NPM
The first step is to install node.js and NPM on your Mac or Linux (Ubuntu/Debian) device.

#### Mac
For mac, you can download the installer [here](https://nodejs.org/download/). Be sure to download a compatible version (usually the latest stable release works). After that, open the download and run the installer. The node.js install comes with NPM as well, so this is the only thing you have to do.

#### Linux (Debian or Ubuntu)

Install curl
```
sudo apt-get update
sudo apt-get install curl
```

Install nodejs 0.12.x
```
# Note the new setup script name for Node.js v0.12
sudo curl -sL https://deb.nodesource.com/setup_0.12 | sudo bash -

# Then install with:
sudo apt-get install -y nodejs
```

Fix global npm package sudo rights
```
# Make a directory for global installations
mkdir ~/npm-global

# Configure npm to use the new directory path
npm config set prefix '~/npm-global'

# Open or create a ~/.profile file and add this line
export PATH=~/npm-global/bin:$PATH

# Back on the command line, update your system variables
source ~/.profile
```

> We advise to check if your global NPM install folder can be used without sudo rights!

Optionally you can install the build-tools package:

```
apt-get install --yes build-essential
```

---

### Install formide-client
After installing, you can download and install formide-client via NPM with just one command:

```
npm install -g formide-client
```

We automatically run post install scripts to create the needed folders and files and check your system.
Also, add the following line to your `.bashrc` file:

```
export PATH=~/npm-global/bin:$PATH
```

If you run the npm install command after doing this, everything should install fine.

---

### Run the client
Running the client is really simple:

```
formide-client
```

---

### Extra

To make sure your user can access a serial device on Linux:
```
sudo usermod -a -G dialout USER_NAME
```

To autoboot formide-client on device boot, add the following lines to /etc/rc.local:
```
export PATH=~/npm-global/bin:$PATH
formide-client &
exit 0
```