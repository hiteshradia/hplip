# hplip
hplip 3.20.9 for Raspberry Pi
HP Linux Imaging and Printing 

Cloned from https://sourceforge.net/projects/hplip/files/hplip/3.20.9/

This Repo is published Under the same License as HPLIP
https://developers.hp.com/hp-linux-imaging-and-printing/IsHPLIPLicensed.html

## DISCLAIMER:- NO LIABILITY for any consequences of using ths software

## Note
**I have installed this on raspberry pi Zero W with raspbian OS lite andusing an HP 2300 series USB (non Wifi) Printer/ Scanner to Print and Scan over Wifi as a Shared Printer. Try this repo and report ansy issues you face. Pease include your Board, OS and Python/qt version with full logs when reporting, Enjoy/!**

## How to install hplip 3.20.9 on raspberry pi raspbian lite OS

### PREREQUISITES
**1.Use the exact version of raspbian lite, as later version "bullseye" is not working for this hplip installation yet.
Raspi OS lite Debian buster 10.11.**

https://downloads.raspberrypi.org/raspios_lite_armhf/images/raspios_lite_armhf-2021-05-28/2021-05-07-raspios-buster-armhf-lite.zip

**if you wish to enable wifi and ssh in a headless rpi see the below hints**
```
https://howchoo.com/g/ndy1zte2yjn/how-to-set-up-wifi-on-your-raspberry-pi-without-ethernet
https://howchoo.com/g/ote0ywmzywj/how-to-enable-ssh-on-raspbian-without-a-screen
```

**2. Set root password on raspberry pi.(will be needed during installation)**
```
pi@raspberrypi:~ $ sudo -s
root@raspberrypi:/home/pi# passwd
New password:
Retype new password:
passwd\: password updated successfully
```
**3 Get dependencies, as some commands within hlip installation are different**
```
sudo apt-get -y update
sudo apt-get -y upgrade
sudo reboot

sudo apt-get install -y ghostscript ghostscript-cups ghostscript-x libcups2-dev cups-bsd cups-client libusb-1.0.0-dev libtool libtool-bin libcupsimage2 libcupsimage2-dev libjpeg62-turbo-dev libssl-dev libsnmp-dev snmp libsane-dev libavahi-client-dev libavahi-core-dev libavahi-common-dev sane avahi-utils sane-utils xsane cups python-qt4-dbus python-notify

sudo apt-get install -y python-pil
sudo apt-get install -y python-skimage
sudo apt-get install -y git vim
```
### INSTALL
**4. git clone this repo and run install.py**
```
git clone https://github.com/hiteshradia/hplip.git
Cloning into 'hplip'...
remote: Enumerating objects: 2646, done.
remote: Counting objects: 100% (2646/2646), done.
remote: Compressing objects: 100% (2136/2136), done.
remote: Total 2646 (delta 510), reused 2618 (delta 495), pack-reused 0
Receiving objects: 100% (2646/2646), 24.71 MiB | 1.05 MiB/s, done.
Resolving deltas: 100% (510/510), done.
Checking out files: 100% (2578/2578), done.


cd hplip/
./install.py  -n
```
## Answer the questions asked by installer as below.


>pi@raspberrypi:~/gitcheckout/hplip $ ./install.py -n
>
>HP Linux Imaging and Printing System (ver. 3.20.9)
>HPLIP Installer ver. 5.1
>
>Copyright (c) 2001-18 HP Development Company, LP
>This software comes with ABSOLUTELY NO WARRANTY.
>This is free software, and you are welcome to distribute it
>under certain conditions. See COPYING file for more details.
>
>Installer log saved in: hplip-install_Fri-10-Dec-2021_17:57:10.log
>
>\
>note: Defaults for each question are maked with a '\>\*'. Press <enter> to accept the default.
>error: debian-10.11 version is not supported, so all dependencies may not be installed. However trying to install using debian-10.4 version packages.
>
**Press 'y' to continue auto installation. Press 'n' to quit auto instalation(y=yes, n=no\*): y**
>
>INSTALLATION MODE
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>Automatic mode will install the full HPLIP solution with the most common options.
>Custom mode allows you to choose installation options to fit specific requirements.
>
**Please choose the installation mode (a=automatic\*, c=custom, q=quit) : c**
>
>
>INTRODUCTION
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>This installer will install HPLIP version 3.20.9 on your computer.
>Please close any running package management systems now (YaST, Adept, Synaptic, Up2date, etc).
>
>
>DISTRO/OS CONFIRMATION
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>Distro appears to be Debian 10.11.
>
**Is "Debian 10.11" your correct distro/OS and version (y=yes\*, n=no, q=quit) ? n**
>
>
>DISTRO/OS SELECTION
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>Choose the name of the distro/OS that most closely matches your system:
>
>Num.  Distro/OS Name
>
>\-\-\-\-  \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>0     Mepis                   
>1     Debian                  
>2     SUSE Linux              
>3     Mandriva Linux          
> ... 
>
**Enter number 0...15 (q=quit) ?1**
>
>Choose the version of "Debian" that most closely matches your system:
>
>Num.  Distro/OS Version                       
>
>\-\-\-\-  \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>0     Unknown or not listed                   
>1     10.0 ("Buster", Released 22/07/2017)    
>2     10.1 ("Buster", Released 22/07/2017)    
>3     10.2 ("Buster", Released 22/07/2017)    
>4     10.3 ("Buster", Released 08/02/2020)    
>5     10.4 ("Buster", Released 09/05/2020)    
> ...  
>44    9.9 ("Stretch", Released 22/07/2017)    
>
**Enter number 0...44 (q=quit) ?5**
>
>Distro set to: Debian 10.4
>
>
>DRIVER OPTIONS
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
**Would you like to install Custom Discrete Drivers or Class Drivers ( \'d\'= Discrete Drivers\*,\'c\'= Class Drivers,'q'= Quit)?   : d**
>
>Initializing. Please wait...
>
>
>SELECT HPLIP OPTIONS
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>You can select which HPLIP options to enable. Some options require extra dependencies.
>
**Do you wish to enable \'Network\/JetDirect I\/O\' \(y\=yes\*, n\=no, q\=quit\) \? y**
  
**Do you wish to enable \'Graphical User Interfaces (Qt4)\' (y=yes\*, n=no, q=quit) ? y**
  
**Do you wish to enable 'PC Send Fax support' (y=yes\*, n=no, q=quit) ? n**
  
**Do you wish to enable 'Scanning support' (y=yes\*, n=no, q=quit) ? y**
  
**Do you wish to enable 'HPLIP documentation (HTML)' (y=yes\*, n=no, q=quit) ? n**
>
>
>
>ENTER ROOT/SUPERUSER PASSWORD
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
**Please enter the root/superuser password\:**
> 
>
>INSTALLATION NOTES
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>NOTE: Disable the CD Sources in your apt sources.list or the install will fail and hang.
>
**Please read the installation notes. Press \<enter\> to continue or 'q' to quit: \<enter\>**
>
>
>SECURITY PACKAGES
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>AppArmor is installed. 
>AppArmor protects the application from external intrusion attempts making the application secure
>
**Would you like to have this installer install the hplip specific policy/profile (y=yes\*, n=no, q=quit) ? y**
>
>
>RUNNING PRE-INSTALL COMMANDS
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>OK
>
>
>RUNNING HPLIP LIBS REMOVE COMMANDS
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>sudo apt-get remove libhpmud0 libsane-hpaio
>sudo apt-get remove libhpmud0 libsane-hpaio \( hp_libs_remove step 1\)
>
>OK
>
>
> MISSING DEPENDENCIES
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>Following dependencies are not installed. HPLIP will not work if all REQUIRED dependencies are not installed and some of the HPLIP features will not work if >OPTIONAL dependencies are not installed.
>Package-Name         Component            Required/Optional
>
**Do you want to install these missing dependencies (y=yes\*, n=no, q=quit) ? y**
>
>
>INSTALL MISSING REQUIRED DEPENDENCIES
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>note: Installation of dependencies requires an active internet connection.
>
>
>RUNNING SCANJET DEPENDENCY COMMANDS
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>su -c \"apt-get install --force-yes -y python-pip\" (Scanjet-depend step 1)
>
>su -c \"pip install \-\-upgrade pip\" (Scanjet-depend step 2)
>
>su -c \"apt-get install \-\-force-yes -y libleptonica-dev\" (Scanjet-depend step 3)
>  ...
>su -c \"pip install scikit-image\" (Scanjet-depend step 13)
>
>su -c \"pip install scipy\" (Scanjet-depend step 14)
>
>OK
>
>
>READY TO BUILD AND INSTALL
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>
>
**Ready to perform build and install. Press \<enter\> to continue or \'q\' to quit: \<enter\>**
>
>
>PRE-BUILD COMMANDS
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>OK
>
>
>BUILD AND INSTALL
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
```
Running './configure --with-hpppddir=/usr/share/ppd/HP --prefix=/usr --enable-qt4 --disable-qt5 --disable-doc-build --disable-cups-ppd-install --disable-foomatic-drv-install --disable-libusb01_build --disable-foomatic-ppd-install --disable-hpijs-install --disable-class-driver --disable-udev_sysfs_rules --disable-policykit --enable-cups-drv-install --enable-hpcups-install --enable-network-build --enable-dbus-build --enable-scan-build --disable-fax-build --enable-apparmor_build'
```
>
>Please wait, this may take several minutes\.\.\.
>Command completed successfully.
>
>Running 'make'
>Please wait, this may take several minutes\.\.\.
>Command completed successfully.
>
>Running 'su -c "make install"'
>Please wait, this may take several minutes...
>Command completed successfully.
>
>
>Build complete.
>
>
>
>POST-BUILD COMMANDS
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>OK
>
>
>HPLIP UPDATE NOTIFICATION
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
**Do you want to check for HPLIP updates\?. (y=yes\*\, n=no) \: n**
>
>
>RESTART OR RE-PLUG IS REQUIRED
>
>-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-
>
>If you are installing a USB connected printer, and the printer was plugged in when you started this installer, you will need to either restart your PC or unplug >and
>re-plug in your printer (USB cable only). If you choose to restart, run this command after restarting: hp-setup (Note: If you are using a parallel connection, >you will
>have to restart your PC. If you are using network/wireless, you can ignore and continue).
>
**Restart or re-plug in your printer (r=restart, p=re-plug in\*, i=ignore/continue, q=quit) \: r**
  
 #### \*\* At the end if hp-setup fails, you may need to run hp-setup as root/sudo. See LOG/WORKINGLOG.txt for details.
 
 **After doing cupsctl --share-printers able to see the printer in CUPS Web https\:\/\/\<IP of raspberryPi>\\:631**
 

  
  ![cups_rpi](https://github.com/hiteshradia/hplip/raw/main/LOG/cups_rpi.jpg)
