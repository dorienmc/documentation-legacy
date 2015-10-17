---
## Update client device
This manual explains step by step how to update a device running the formide-client application.
This works with prototypes of The Element as well as custom devices like Raspberry Pi 2 or Beagle Bone Black.
In the future, The Element will have automatic updates, so no manual updating is required.

---
### Get access

#### SSH (Linux and Mac)
The safest way to get access to your device is by using SSH. You can run the following command on your Linux or Mac machine to start an SSH session. You have to know the IP address of your device and be in the same network. The username for the prototype Element is `debian`.

```
ssh debian@YOUR_DEVICE_PI
```

If everything goes well, you'll be prompted to enter a password. For the prototype Element, the password is `debian`.

#### Windows
For Windows, there's a tool called [PuTTy](http://www.putty.org) that you can download to run an SSH client (since Windows doesn't support SSH out of the box). In this tool, you can enter the username (`debian` on The Element), password (`debian`) and IP address of the device to get access. When connection is successful, PuTTy will open a command line prompt and from there on, the process is the same.

#### Screen
Another method that only works with the prototype Element is using `screen`. Screen is a tool that allows you to start a cross-device shell session. We configured The Element to accept screen connections via the USB slave port. You can connect The Element's power cable (micro USB to USB type b) to your computers USB port. Then, running the following command on Linux or Mac
