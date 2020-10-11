# Native Linux install on Samsung Galaxy Tab 2 7.0 10.0 (unified) using PostmarketOS

**Warning**: _Test on your own risk. Works at least in my Samsung Galaxy Tab 2 7.0._

This is a guide about how to run Native Linux on the Samsung Galaxy Tab 2.

According to Wikipedia:
*"" PostmarketOS (stylized as postmarketOS and abbreviated as pmOS) is a free and open-source operating system under development primarily for smartphones, based on the Alpine Linux distribution. ""*

https://wiki.postmarketos.org/wiki/Samsung_Galaxy_Tab_2_10.1_(3G_and_Wifi)_(samsung-espresso10)

## What you will need:

- A rooted Samsung Galaxy Tab 2 with TWRP installed.
- A Linux computer

Note: I have used a computer with Linux in this guide. I don't know if it can be done with other OS because I haven't tested it.

There are two ways of doing this, ***using my prebuilt image file or doing everything from scratch***.

## Using my prebuilt image file (flashes on /system)

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

**1. Install pmbootstrap**: https://wiki.postmarketos.org/wiki/Installing_pmbootstrap<br/>
**2. Create the XFCE image**:

<pre>$ pmbootstrap init</pre>

Now put exactly the text inside the square brackets "[ ]" in each prompting line. For example:

<pre>[12:53:27] Location of the 'work' path. Multiple chroots (native, device arch, device rootfs) will be created in there.
[12:53:27] Work path [/home/user/.local/var/pmbootstrap]: 
[12:53:28] NOTE: pmaports path: /home/user/.local/var/pmbootstrap/cache_git/pmaports
[12:53:28] Choose the postmarketOS release channel.
[12:53:28] Available (2):
[12:53:28] * edge: Rolling release channel
[12:53:28] * stable: Stable release channel (first beta v20.05, does not have many devices yet)
[12:53:28] Channel [edge]: 
[12:53:29] Choose your target device vendor (either an existing one, or a new one for porting).
[12:53:29] Available vendors (54): acer, alcatel, amazon, arrow, asus, bq, chuwi, cubietech,
essential, fairphone, finepower, fly, fujitsu, google, gp, hisense, htc, huawei, infocus, jolla,
leeco, lenovo, lg, medion, meizu, motorola, nextbit, nobby, nokia, oneplus, oppo, ouya,
pine64, planet, purism, qemu, raspberry, samsung, semc, sharp, sony, surftab, t2m,
tablet, teclast, tokio, vernee, wiko, wileyfox, wingtech, xiaomi, yu, zte, zuk
[12:53:29] Vendor [samsung]: 
[12:53:35] Available codenames (57): a3lte, a3ulte, a5lte, a5ulte, a5y17lte, apexq, ariesve, baffinlite, chagallwifi, codina, crespo, espresso10, expressatt, golden, 
gt510wifi, gtel3g, gtelwifi, gts210velte, gts210vewifi, hero2lte, herolte,
i747m, i8200, i9003, i9070, i9100, i9195, i927, i9305, j1mini3g, j3nxlte, 
j53g, j5nlte, jflte, klte, kminilte, kylepro, kylessopen, kylevess, lt01wifi,
lt023g, maguro, manta, matissevewifi, matissewifi, ms013g, n5110, n7100, nevisp, p4wifi, royss, s3ve3g, s6500d, serranodsdd, serranovelte, skomer, zanin
[12:53:35] Device codename [espresso10]: 
[12:53:36] This device has proprietary components, which trade some of your freedom with making more peripherals work.
[12:53:36] We would like to offer full functionality without hurting your freedom, but this is currently not possible for your device.
[12:53:36] device-samsung-espresso10-nonfree-firmware: Wifi firmware
[12:53:36] Enable this package? (y/n) [y]: 
[12:53:37] Username [samsung]: 
[12:53:38] Available user interfaces (13): 
[12:53:38] * none: No graphical environment
[12:53:38] * fbkeyboard: Plain framebuffer console with touchscreen keyboard support
[12:53:38] * gnome: (Wayland) Gnome Shell
[12:53:38] * i3wm: (X11) Tiling WM (keyboard required)
[12:53:38] * kodi: (Wayland) 10-foot UI useful on TV's
[12:53:38] * mate: (X11) MATE Desktop Environment, fork of GNOME2 (stylus recommended)
[12:53:38] * phosh: (Wayland) Mobile UI developed for the Librem 5 (works only with numeric passwords!)
[12:53:38] * plasma-bigscreen: (Wayland) 10-feet variant of Plasma, made for big screen TVs
[12:53:38] * plasma-mobile: (Wayland) Mobile variant of KDE Plasma (does not run without hardware acceleration, allows only numeric passwords!)
[12:53:38] * shelli: Plain console with touchscreen gesture support
[12:53:38] * sway: (Wayland) Tiling WM, drop-in replacement for i3wm (DOES NOT RUN WITHOUT HW ACCELERATION!)
[12:53:38] * sxmo: (X11) Simple X Mobile: Mobile environment based on simple & suckless software (best compatibility on pinephone)
[12:53:38] * weston: (Wayland) Reference compositor (demo, not a phone interface)
[12:53:38] * xfce4: (X11) Lightweight desktop (stylus recommended)
[12:53:38] User interface [xfce4]: 
[12:53:39] Additional options: boot partition size: 128 MB, parallel jobs: 5, ccache per arch: 5G
[12:53:39] Change them? (y/n) [n]: 
[12:53:40] Additional packages that will be installed to rootfs. Specify them in a comma separated list (e.g.: vim,file) or "none"
[12:53:40] Extra packages [network-manager-applet,onboard,midori,gimp,abiword,gnumeric,baobab,nano,gnome-keyring]: 
[12:53:44] Your host timezone: Europe/Madrid
[12:53:44] Use this timezone instead of GMT? (y/n) [y]: 
[12:53:45] Device hostname (short form, e.g. 'foo') [samsung-espresso10]: 
[12:53:46] Would you like to copy your SSH public keys to the device? (y/n) [n]: 
[12:53:47] After pmaports are changed, the binary packages may be outdated. If you want to install postmarketOS without changes, reply 'n' for a faster installation.
[12:53:47] Build outdated packages during 'pmbootstrap install'? (y/n) [y]: 
[12:53:50] Zap existing chroots to apply configuration? (y/n) [y]: 
</pre>

**2. Go to TWRP recovery and flash the XFCE image**:

- Now make an android zip file for flashing in recovery:

	https://wiki.postmarketos.org/wiki/Installation_from_recovery_mode

	<pre>$ pmbootstrap install --android-recovery-zip </pre>

- Then, go to TWRP recovery and flash the image using sideload:

	<pre>$ pmbootstrap flasher --method=adb sideload</pre>

- If adb sideload hasn't worked for you, try:

	<pre>$ pmbootstrap export && adb push /tmp/postmarketOS-export/pmos-samsung-espresso10.zip /sdcard</pre>

**3. Reboot and done!**


##  Optional: How to do your own PostmarketOS espresso10 prebuilt image file

### 1. Make your necessary changes.

### 2. Supposing postmarketOS is booting on your /system partition, go to recovery and with your computer do:

**Note: Before doing this, make sure you have done a "sudo poweroff" instead of "sudo reboot" in your PostmarketOS system to avoid image mounting error. **

<pre>$ adb shell </pre>
<pre># dd if=/dev/block/mmcblk0p9 of=/sdcard/custom-pmos-samsung-espresso10.img</pre>

**Then in your computer:**

<pre>$ adb pull /sdcard/custom-pmos-samsung-espresso10.img ~/Downloads/</pre>

### 3. Mount the image using an image mounter and go to pmOS_root partition.

### 4. Copy pmOS_boot files into pmOS_root/boot:

<pre>$ cd /media/user/pmOS_boot/</pre>
<pre>$ sudo cp boot.img-samsung-espresso10 initramfs-samsung-espresso10 initramfs-samsung-espresso10-extra vmlinuz-samsung-espresso10 /media/user/pmOS_root/boot/</pre>

### 5. Make a tar of that partition:

<pre>$ cd /media/user/pmOS_root/</pre>
<pre>$ env GZIP=-9 sudo tar -cvzf ~/Downloads/rootfs.tar.gz *</pre>

### 6. Generate an android recovery zip and replace its original rootfs.tar.gz with yours.

<pre>$ pmbootstrap install --android-recovery-zip && pmbootstrap export</pre>
<pre>$ mkdir -p /tmp/postmarketOS/ && cd /tmp/postmarketOS-export/pmos/</pre>
<pre>$ unzip ../pmos-samsung-espresso10.zip</pre>
<pre>$ cp ~/Downloads/rootfs.tar.gz rootfs.tar.gz</pre>

### 7. Avoid creating home folder (because it already exists)

Remove the following content in /tmp/postmarketOS-export/pmos/chroot/bin/pmos_install and save the file:
<pre>ui_print "Creating home folder..."
mkdir /mnt/pmOS/home
user="$(awk -F ':' '$3 == "10000" {print $1}' /mnt/pmOS/etc/passwd)"
cp -a /mnt/pmOS/etc/skel /mnt/pmOS/home/"$user"
chown -R 10000 /mnt/pmOS/home/"$user"</pre>

### 8. Test and done!
