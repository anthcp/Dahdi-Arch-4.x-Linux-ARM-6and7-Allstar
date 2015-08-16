Dahdi-Arch-4.x-Linux-ARM-6and7-Allstar
======================

Package for Dahdi Arch kernel drivers for Allstar Asterisk ARM versions from this repo.
Running "makepkg" as a non root user will create a Dahdi package for Arch Linux 4.x ( only tested for <4.1) 

It works for Arch ARM7 & ARM6 for Raspberry PI model 2 and other ARM6/7 models (for other ARM7 devices, just select the correct linux-headers when setting up the development enviroment)

It will download the dahdi source code if required...
After package install a reboot will be required to initalze the dadhi although you can test this by doing "sudo modprobe dahdi" and then doing "ls /dev/dahdi/*" which should show the dahdi devices.

Detailed procedure, assuming you have arch linux already running...

1. Install development enviroment while logged in as root e.g pacman -S base-devel
 
2. Install Linux headers (make sure you select the raspberry PI version) and other dependencies e.g pacman -S linux-headers alsa-lib alsa-oss

3. Install Git e.g pacman -S git

4. Create a normal user (test is the username) e.g useradd -m test

5. Switch to this user e.g su - test

6. Download this package e.g git clone https://github.com/anthcp/Dahdi-Arch-4.x-Linux-ARM-6and7-Allstar.git

7. Change directory to the git directory e.g cd Dahdi-Arch-4.x-Linux-ARM-6and7-Allstar

8. Run the makepkg command e.g makepkg

9. On successfull completeion of makepkg, type exit, cd to /home/test/Dahdi-Arch-4.x-Linux-ARM-6and7-Allstar and run pacman --force -U dahdi-allstar-2.9.1.1-2-armv7h.pkg.tar.xz 

10. Dahdi Kernel drivers for Allstar is now installed...

Will update as required.

Anthony, VK2ACP

