# KALI LINUX SETUP ON VIRTUALBOX;
 Kali Linux is a Debian-based Linux distribution designed specifically for penetration testing, cybersecurity research, and ethical hacking. It has over 200 testing tools pre-installed on it; Nmap for vulnerability scanning, Wireshark for packet analysis, Metasploit for exploitations etc. Before installation starts, ensure host PC has some settings fixed up;

 (i) Ensure your PC supports virtualization (Intel VT-x or AMD-V) and enable it in the BIOS/UEFI settings if disabled. (Virtualization makes sure testing is conducted in a safe environment, and for easy recovery via snapshots).
 
 (ii) RAM must be at least 8GB
 
 (iii) Enough disk space for kali linux & host PC itself.
 
 
 Here's how to install Kali Linux Virtual Machine on VirtualBox;

* Download & install the latest version from [VirtualBox Official website](https://www.virtualbox.org/). Download what's compatible with the host PC; MacOS, Windows, Linux etc
* Download Kali Linux latest ISO file from the [Official Kali Linux website](https://www.kali.org/). Ensure you download the version compatible with the PC; 64-bit, 32-bit or any other version.

#### NOW AT VIRTUALBOX HOMEPAGE;
* Click on new
* Fill in the name & OS options appropriately; name, folder, type-Linux, version-Debian (64-bit). ignore the ISO image option for now. click on next >>
* Allocate the RAM (base memory) & Processor (CPU) depending on host PC's memory. click on next >>
* Create a Virtual Hard Disk of not less than 35GB disk size, depending on host PC's memory also. click FINISH.

#### NOW AT VIRTUALBOX HOMEPAGE, click on SETTINGS;
* Under General, click on Advanced and set "shared clipboard & drag'N'drop" as BIDIRECTIONAL
* Under Display, set the video memory to maximum (128), enable 3D Acceleration
* Under Storage, click on Empty (the IDE Controller in VirtualBox), then on the right side, click on the blue disk icon to load the ISO file you already downloaded
* Under Network, most preferably, use either NAT Network, NAT or Bridge Adapter. click OK

#### NOW AT VIRTUALBOX HOMEPAGE, click on START >>>
* Select the "Graphical Install" option
* Select the appropriate options (Language, Location, Keyboard Language, Host Name-Kali, Domain Name-leave empty, User Account & Password)
* Partition Disks >> Guided - use entire disk >> click continue >> All files in one partition >> Yes 
* Software Selection >> Gnome >> click continue 
* Install the GRUB boot loader >> Yes >> /dev/sda {ata-VBox} >>> click FINISH. VM will Reboot

#### NOW AT KALI LINUX HOMEPAGE after successful installation >>

* Update your VM >> `sudo apt update && sudo apt upgrade -y`

* Reboot your VM >> `sudo reboot`

* Install Linux Headers >> `sudo apt-get install linux-headers-$(uname r)`

* Install VBox Guest Additions >> at top right corner go-to Device >> click Insert Guest Additions CD Image. Then Open terminal >>

`cd /media/cdrom` >> changes the current directory to "/media/cdrom" commonly used to access the "Guest Additions ISO when inserted to the VM"

`sudo ./VBoxLinuxAdditions.run` >> it executes scripts & provide additional features like drag-n-drop, shared folder & shared clipboard 

`sudo reboot` >> restarts the VM to effect all changes made to the system


      Having done all these, Kali Linux should be 100% functioning on VirtualBox.


 <img src="Screenshot from 2025-01-16 11-09-55.png" alt="alt text" width="750">