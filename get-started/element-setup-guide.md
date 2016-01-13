
---
# Element setup guide
This guide explains step by step how to setup a new Element. It also described any known issues you might encounter during the setup.

---
## Power on
The first thing to do after taking The Element out of the box is plugging it in a power adapter. The Element comes with a Micro USB to USB type B cable (normal USB) which you can put in any USB adapter that delivers enough current (1.5A or more). If The Element boots correctly, you should see the LED flash yellow and then green. We're working on more LED integration to indicate more statuses.

---
## Connect to cloud
Connecting your Element to your cloud account requires the following things: a WiFi network with WPA-2 security (common for all home and office routers). Open networks, enterprise networks that require a certificate or older networks with WEP security are not supported at this moment.

Go to platform(-dev).formide.com and log in with your FORMIDE cloud account. If you don't have an account yet, you can also create it right there (or log in with Facebook or Google). After creating account, you can immediately log in and continue the setup.

Make sure you powered on The Element and that it sends out it's own WiFi network with a name in the following format: `The-Element-XXXXXX`. Then go to manage -> devices and switch your WiFi to connect to The Element's own network. Then you can click on 'Setup a new device'. This will redirect to a page on The Element where you can setup the WiFi network that The Element should connect to. When you have entered the correct credentials, The Element will connect to that network and after a while it's own network will drop. You will be redirected back automatically to the platform to finish the setup flow. Just click 'finish setup' and you're all set!

---
## Connect printer
To connect the printer, just plug it into The Element's USB port (or via a USB hub if you want to use multiple printers). After plugging it in, you should see a notification in the interface (platform.formide.com) that an unknown printer was found. Click it to setup this printer and select the type or fill in the settings manually. A few seconds after clicking 'setup', it should appear as 'online' in the right sidebar. Now you can 'select' it and start using the printer.
---
## Start first print
In order to start you first print, you need to have the following items ready: a setup printer (see previous step), at least 1 material setting and at least 1 sliceprofile. To make your life easier, we also added over 60 material presets that you can choose from and copy to your account. Next to that, you can create a new sliceprofile based on our defaults or import your current profile from Cura (other slicers coming soon). Creating and managing these settings can be found under settings -> materials/printers/sliceprofiles.

When you have created your material and sliceprofile settings you can upload your first file. To do this, go to the files page and click 'upload a new file' or just drag and drop a file (.stl or .gcode) to the browser.

To slice and print a .stl file, hover over the file and click 'print'. This will open the printjob window in which you can configure how your file is printed and with which printer, material and slicesettings. You can also tweak some settings in the advanced menu like wether to use support material or not. Once you are happy with your settings, click 'slice' at the top and FORMIDE will process the 3D file for you (using the Katana cloud) and give you a notification when that's done. After slicing, the printjob appears in the right side list in the file details window (double click a file). Here you can add the printjob to the queue of the selected printer (the printer should be online and idle!). Once an item is in the queue, you can click 'start' to start the print. Make sure your printer is cleared!
