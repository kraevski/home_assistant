\# 🕒 Running Home Assistant on Xiaomi Mi Smart Clock



This guide will walk you step-by-step through flashing \*\*LineageOS\*\* onto the \*\*Xiaomi Mi Smart Clock\*\* and installing \*\*Fully Kiosk Browser\*\* to display the \*\*Home Assistant Lovelace UI\*\*.



> ⚠️ \*\*WARNING\*\*: This is an advanced process. You may brick your device or lose your data if you do not follow the steps carefully. Proceed at your own risk.



---



\## 🔧 Requirements



\- A \*\*PC or laptop\*\* that can boot from USB

\- \*\*2 USB drives\*\*:

&nbsp; - One for the \*\*Live DVD V6\*\* image (bootable)

&nbsp; - One for storing backups, firmware, and APKs

\- Xiaomi Mi Smart Clock



---



\## 📥 Files to Download



| Type | Description | Link |

|------|-------------|------|

| Live DVD V6 | Flashing OS Environment | \[Download here](https://github.com/bkerler/mtkclient#installation) |

| LineageOS | Custom Android OS | \[Download here](https://androidfilehost.com/?fid=10620683726822080854) |

| Fully Kiosk Browser | Displays Home Assistant UI | \[Download APK here](https://www.fully-kiosk.com/en/#download) |



---



\## 🖥️ Prepare USB Drives



1\. Flash the \*\*Live DVD V6 .iso\*\* to the first USB drive using \[Balena Etcher](https://etcher.io).

2\. On the second USB drive:

&nbsp;  - Copy the extracted `boot.img`, `super.img`, and `vbmeta.img` files from the LineageOS zip.

&nbsp;  - Copy the Fully Kiosk Browser `.apk` file.



---



\## 🚀 Boot into Live DVD



1\. Insert the \*\*Live DVD USB\*\* into your computer and boot from it.

2\. Login with:

&nbsp;  - \*\*Username\*\*: `user`

&nbsp;  - \*\*Password\*\*: `user`

3\. Disable automatic suspend:

&nbsp;  - Right-click Desktop → `Display Settings` → `Power`

&nbsp;  - Turn off \*\*Automatic Suspend\*\*

&nbsp;  - Set \*\*Screen Blank\*\* to \*\*Never\*\*

4\. Change keyboard layout to English:

&nbsp;  - Click `de` on the menu bar → Choose `en`



---



\## 💾 Backup the Clock



\### Option 1: GUI (Recommended)



1\. Right-click `mtkclient.desktop` → `Show in Files`

2\. Double-click the \*\*green\*\* `MTK Client` icon to open MTK GUI

3\. Connect your Mi Smart Clock while holding \*\*Volume +\*\*

4\. Wait until the clock is detected (should show `MT8167/MT8516/MT8362` and `Bootrom mode`)

5\. Insert your second USB (backup) drive

6\. Backup steps:

&nbsp;  - `Flash tools` tab → `Read flash` → Save to USB drive

&nbsp;  - Also run:

&nbsp;    - `Read preloader`

&nbsp;    - `Read boot2`

&nbsp;  - `Read partition(s)` tab → Check \*\*Select all partitions\*\* → Click `Read partition(s)`

7\. When done, disconnect the clock



\### Option 2: Terminal



```bash

\# Inside Live DVD environment:

cd mtkclient



\# Create virtual environment

sudo apt install python3.12-venv

python3 -m venv mtk\_venv

source mtk\_venv/bin/activate



\# Backup full flash

python mtk.py rf flash\_mico\_x04g.bin --noreconnect



---



\## ⚙️ Install Lineage OS:


1. Erase old partitions:


python mtk.py e metadata,userdata,md\_udc --noreconnect





2\. Unlock the bootloader:



python mtk.py da seccfg unlock --noreconnect



python mtk.py reset



3\. Unplug the clock. Again plug it back in while holding vol up and volume down. 
4. You will see "no command" screen on clock Press "mute" and "volume up" to enter recovery mode. 

5\. Use “volume up” and “volume down” in recovery to select "reboot to bootloader"

6\. After some time, clock will enter fastboot mode (it will be indicated with a small text at the bottom of the clock screen).



\## 📦 Flash LineageOS:

1. Go to the folder in your USB drive where you copied the three .img files as per point 4 by clicking on the USB drive icon in your desktop, but do not enter the folder itself. Right click on such folder (or the USB drive itself if you copied the .img files in USB drive root) and select “Open in Terminal”.



2\. Flash LineageOS by executing the following commands one by one:



```bash

fastboot flash boot boot.img

fastboot flash super super.img

fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img

fastboot reboot



3\. If everything goes well, Lineage will boot in a few minutes. BE PATIENT! Be advised that Lineage boot times are long. Expect to be seeing the “Orange State” screen displayed for a few minutes, although it says that it will boot in 5 seconds.Furthermore, you will see a blank screen, Lineage logo animation and a white rectangle screen form some time. Again… BE PATIENT! The whole process will take 5-6 minutes from the moment that you plug the device in to the moment where the startup wizard starts at.


##📱 Install Fully Kiosk Browser



1. Slide to the left so you can go to the second desktop. You will see there the settings icon. Click on it. Go to the “Device information” option at the bottom of the screen and click on it. Slide down to the latest option named “Compilation number”. Click on it several times until you see a message confirming that the developer options have been enabled.
2. Go back to the previous menu. Find the “System” menu and enter. Find the “Developer options” and enter. You won’t be able to slide down on this screen (at least I haven’t been able to), so click on the magnifier icon at the top right of the screen. Type “USB” on the search field. Once results are displayed, scroll down until you find the “USB debugging” option. Enable the option, accept the warning and exit to the desktop clicking on the “circle” icon at the bottom of the screen.
3. Go back to the computer where the Live DVD/USB is running. Make sure that the Clock is still connected. If you have connected to the power supply for setting up Lineage, unplug it, connect it back to the computer and wait for the clock to load the Lineage desktop.
4. Once everything is on place, we will install Fully Kiosk on the clock trough adb from the computer. For that, we will use the same “right click > Open in Terminal” option we’ve been using along this guide at the USB folder where the Fully Kiosk apk was copied to (point 5). On the terminal type the following:

   ```bash
   adb install Fully-Kiosk-Browser-v1.58.3.apk
   
5. Once done, Fully Kiosk is installed. You can go back to the clock, slide the finger up through the screen to reveal the applications and click on the Fully Kiosk Browser menu.
6. Type your Home Assistant instance URL on the “Start URL” field, make sure that the Fullscreen Mode is enabled, slide down and hit “Start Using Fully”.
   

\## 💬 Helpful Threads


\[Home Assistant Forum Thread](https://community.home-assistant.io/t/hack-mi-smart-clock-to-display-lovelace-ui/)

\[XDA Developers Guide](https://xdaforums.com/t/xiaomi-mi-smart-clock-development-guide-gsi.4629771/)



