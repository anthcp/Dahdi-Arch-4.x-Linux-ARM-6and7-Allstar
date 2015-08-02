Dahdi-linux-allstar-odroid
======================

Package for Dahdi kernel drivers for Allstar...
Running "makepkg" as a non root user will create a Dahdi package for Arch Linux. 
This package contains the Allstar patch  (thanks to Jim Duuuude) to allow dahdi to work with Allstar. 
It works for Arch ARM on Odroid X,X2,X3,U,U2....

It will download the dahdi source code if required...
After package install a reboot will be required.

Detailed procedure, assuming you have arch linux already running...

1. Install development enviroment while logged in as root e.g pacman -S base-devel
 
2. Install Linux headers and other dependencies e.g pacman -S linux-headers-odroid alsa-lib alsa-oss

3. Install Git e.g pacman -S git

4. Create a normal user (test is the username) e.g useradd -m test

5. Switch to this user e.g su - test

6. Download this package e.g git clone https://github.com/anthcp/dahdi-linux-allstar-pi.git

7. Change directory to the git directory e.g cd dahdi-linux-allstar-pi

8. Run the makepkg command e.g makepkg

9. On successfull completeion of makepkg, type exit, cd to /home/test/dahdi-linux-allstar-pi and run pacman --force -U dahdi-allstar-2.9.1.1-1-armv7h.pkg.tar.xz 

Will update as needed.

Anthony, VK2ACP

