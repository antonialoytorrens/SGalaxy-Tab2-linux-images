# Native Linux install on Samsung Galaxy Tab 2 7.0 10.0 (unified) using PostmarketOS

**Warning**: _Test on your own risk. Works at least in my Samsung Galaxy Tab 2 7.0._

This is a guide about how to run Native Linux on the Samsung Galaxy Tab 2.

According to Wikipedia:
*"" PostmarketOS (stylized as postmarketOS and abbreviated as pmOS) is a free and open-source operating system under development primarily for smartphones, based on the Alpine Linux distribution. ""*

https://wiki.postmarketos.org/wiki/Samsung_Galaxy_Tab_2_10.1_(3G_and_Wifi)_(samsung-espresso10)

## What works:

### Mainline (5.17.x kernel, new and well maintained kernel) Port For 7 inch devices (espresso3g, espressowifi)

See https://wiki.postmarketos.org/wiki/Samsung_Galaxy_Tab_2_7.0%22_(samsung-espresso3g), read mainline section.

### Downstream (3.0.x kernel, very old unsupported kernel) Vendor Port For 10 inch devices (espresso10)

See https://wiki.postmarketos.org/wiki/Samsung_Galaxy_Tab_2_7.0%22_(samsung-espresso3g), read downstream section.

We divide this into two categories because the 10 inch devices use different touch and display panels than the 7 inch devices. [Mighty17](https://github.com/MightyM17/) and me only have 7 inch device to test, so feel free to write an issue if you own this device and you want some mainline support for it (you need to be familiar typing commands on Linux terminal to test things, so some Linux experience is appreciated).

## What you will need:

- Bootloader unlocked Samsung Galaxy Tab 2 with TWRP installed. Pick [andi34 (Android-Andi) TWRP if you haven't already](https://www.androidfilehost.com/?w=files&flid=48848&sort_by=date&sort_dir=DESC).
- A Linux computer

Note: I have used a computer with Linux in this guide. I don't know if it can be done with other OS because I haven't tested it.

There are two ways of doing this, ***using my prebuilt image file or doing everything from scratch***.

## Before starting anything

:warning: **If you use my prebuilt image file, mind that you won't have official PostmarketOS support to ask for issues. The easier way is downloading my prebuilt image file, but the recommended way is building everything from scratch.** :warning:

## Using my prebuilt image file (flashes on /system) (NOTICE: 5.17.x flashes on /sdcard due to space issues, so backup before continuing)

**Mainline images (IMPORTANT! THEY DO NOT WORK ON 10-INCH SAMSUNG GALAXY TAB 2 DEVICE, AND READ NOTES, INCLUDED IN THE LINK)**: Download from here: https://sourceforge.net/projects/sgalaxy-tab2-linux-images/files/postmarketOS/mainline/ 

**XFCE**: Download from here:   https://sourceforge.net/projects/sgalaxy-tab2-linux-images/files/postmarketOS/XFCE/pmos-samsung-xfce-espresso10-v2.0.zip

### Then follow these steps:

**1. Go to recovery partition (tested in TWRP)**.

**2. Put the file into /sdcard partition**:

<pre>$ adb push ~/path/of/pmos-samsung-espresso10.zip /sdcard</pre>

*Note: you can also do it with adb sideload.*

**3. Flash the file, reboot and done**.

| **User**     | **samsung** |
|----------|---------|
| **Password** | **samsung** |

##  Doing everything from scratch

Follow the official guide (you may need to search for additional information): https://wiki.postmarketos.org/wiki/Samsung_Galaxy_Tab_2_10.1_(3G_and_Wifi)_(samsung-espresso10).

## Pvrports

Pvrports are additional PostmarketOS aports that need to be build in order to have non-free GPU support with this tablet and other devices that have a PowerVR SGX GPU.
It's **not** supported by official PostmarketOS team due to additional burden mainteinance, here's why: https://gitlab.com/postmarketOS/pmaports/-/issues/1316

Source code: https://gitlab.com/pvrports/pvrports
