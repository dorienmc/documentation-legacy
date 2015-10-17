---
### Download
You can download the latest image [here](#/docs/client/install/beta/).

---

### Install

#### Mac/Linux
You can use dd to copy the downloaded image to and SD card. This process will take a while.
```
sudo dd if=/location/of/downloaded/image of=/dev/diskN bs=4
```

#### Windows
On windows there is a tool available to copy an image to and SD card: [win32diskimager](http://sourceforge.net/projects/win32diskimager/). We advise you to download this to flash the SD card with our image.

---

### Run FORMIDEOS
After flashing the SD card, just insert it in your Raspberry Pi or Beagle Bone. The image includes an autoboot item for the formideos-client process, so after a while, FORMIDEOS should be available at port 8080 at the IP address of your device.