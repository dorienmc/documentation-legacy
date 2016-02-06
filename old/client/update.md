---
## Update client device
This manual explains step by step how to update a device running the formide-client application.
This works with prototypes of The Element as well as custom devices like Raspberry Pi 2 or Beagle Bone Black.
In the future, The Element will have automatic updates, so no manual updating is required.

---
### Get access

#### SSH (Linux and Mac)
The safest way to get access to your device is by using SSH. You can run the following command on your Linux or Mac machine to start an SSH session. You have to know the IP address of your device and be in the same network. The `username` for the prototype Element is `debian`.

```
ssh username@ip_address
```

If everything goes well, you'll be prompted to enter a password. For the prototype Element, the password is `debian`.

#### Windows
For Windows, there's a tool called [PuTTy](http://www.putty.org) that you can download to run an SSH client (since Windows doesn't support SSH out of the box). In this tool, you can enter the username (`debian` on The Element), password (`debian`) and IP address of the device to get access. When connection is successful, PuTTy will open a command line prompt and from there on, the process is the same.

#### Screen
Another method that only works with the prototype Element is using `screen`. Screen is a tool that allows you to start a cross-device shell session. We configured The Element to accept screen connections via the USB slave port. You can connect The Element's power cable (micro USB to USB type b) to your computers USB port. Then, running the following command on Linux or Mac.

```
screen /dev/device_port 115200
```

A new shell session should start, this time inside of The Element. Here you can type the username and password (both `debian`) to log in.

** We advice not to edit any files using screen as this might break the endlines. For example doing this with /etc/rc.local will break the boot sequence of the device after which you can't use it anymore! **

---
### Run the update
Running the update is just a few command in the terminal. Run the following commands one by one. Some commands need to be run as `sudo` and will prompt you for a password. Usually, the password is the same as the one from your current user. In case of The Element, it's `debian`.

#### Stop the current formide-client process
```
sudo pkill -f formide-client
```
This stops the formide-client process currently running. Prevents trying to use the same TCP port twice when manually restarting it after the update.

#### Pull the update from NPM
```
npm install -g formide-client
```
This pull the latest release for formide-client from NPM (Node.js Package Manager). This step will take a while (between 5 and 10 minutes, depending on the speed of your device), so don't be scared when nothing happens for a while.

#### Restart the formide-client process (or reboot)
```
sudo -u debian /home/debian/npm-global/bin/formide-client >formide-client.txt 2>&1 &
```
This starts formide-client with the correct permissions and as the correct user. It also outputs the logs to a file cadded /formide-client.txt which we can use for later analysis. You can also reboot The Element to automatically start the updated formide-client application.

```
sudo reboot
```
