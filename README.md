# hplip
hplip 3.20.9 for Raspberry Pi
HP Linux Imaging and Printing 

Cloned from https://sourceforge.net/projects/hplip/files/hplip/3.20.9/

This Repo is published Under the same License as HPLIP
https://developers.hp.com/hp-linux-imaging-and-printing/IsHPLIPLicensed.html

NO LIABILITY for any consequences of using ths software


## How to install hplip 3.20.9 on raspberry pi raspbian lite OS

### PREREQUISITES
**1.Use the exact version of raspbian lite, as later version "bullseye" is not working for this hplip installation yet.
Raspi OS lite Debian buster 10.11.**

https://downloads.raspberrypi.org/raspios_lite_armhf/images/raspios_lite_armhf-2021-05-28/2021-05-07-raspios-buster-armhf-lite.zip

**2. Set root password on raspberry pi.(will be needed during installation)**
pi@raspberrypi:~ $ sudo -s
root@raspberrypi:/home/pi# passwd
New password:
Retype new password:
passwd: password updated successfully

**3 Get dependencies, as some commands within hlip installation are different**
sudo apt-get -y update
sudo apt-get -y upgrade

sudo apt-get install -y python-pil
sudo apt-get install python-skimage

### INSTALL
**4. git checkout this repo and run install.py**
cd hplip/
./install.py  -n
