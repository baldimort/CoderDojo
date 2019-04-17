Installation Notes for Raspberry Pis used for CoderDojo Sessions.

1) Downloaded image "2017-08-16-raspbian-stretch.img" from:
https://www.raspberrypi.org/downloads/raspbian/

RASPBIAN STRETCH WITH DESKTOP - Image with desktop based on Debian Stretch
Version:August 2017
Release date:2017-08-16
Kernel version:4.9
Release notes:http://downloads.raspberrypi.org/raspbian/release_notes.txt

2) Burnt IMG file to Master 8GB MicroSD card labeled as "00"

3) Booted up and changed the following (via Preferences / Raspberry PI configuration):
- Hostname to "pi00"
- Enabled Camera & SSH (But not VNC due to known issue with taskbar not appearing in "2017-08-16-raspbian-stretch.img")
- Changed the default password for "pi" ID from "raspberry" to "password" (to stop ssh warning messages)

4) Synced up current CoderDojo repository via:
cd /home/pi
git clone https://github.com/markcarline/CoderDojo CoderDojo

5) Created a world in Minecraft for "project03" as magic door mat:
- Start Minecraft / Start game / Create New
- Created a wall with 3x doors and 3x mats (Red / Yellow and Green)
- Tested with project03 that these work.

6) Created backup of "00" MicroSD card image as:
CoderDoJo_Build_v3-00.img

7) Updated build created, added:

a) connected to CODERDOJO wifi / router

b) Update raspbian build via:
sudo apt-get update
sudo apt-get dist-upgrade

c) Added support for the speaker:
sudo apt install pt-speaker

d) Refreshed this CoderDojo repository via:
cd /home/pi
rm -r CoderDojo
git clone https://github.com/markcarline/CoderDojo CoderDojo

8) Created backup of "00" MicroSD card image as:
CoderDoJo_Build_v3-01.img

NOTE:  If you have problems booting the image using a normal HDMI display (rather than the PiTop) edit the config.txt file on the SD card and set:

hdmi_group=2
hdmi_mode=16

9) Created backup of "00" MicroSD card image as:
CoderDojo_Build_v3-03.img
with changes:
- Backup of minecraft world via commands:

cd /home/pi/.minecraft/games/com.mojang/minecraftWorlds
cp -r world world.backup

To delete current "world" Minecraft world & restore from world.backup use new script in
/home/pi/CoderDojo/utils/resetworld.sh
