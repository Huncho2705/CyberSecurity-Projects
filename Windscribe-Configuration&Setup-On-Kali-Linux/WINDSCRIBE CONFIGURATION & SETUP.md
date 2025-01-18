# WINDSCRIBE VPN INSTALLATION, CONFIGURATION & SETUP ON KALI LINUX;
 This is a detailed breakdown on how to properly install, configure and setup Windscribe VPN on a kali linux virtual machine. As a Cybersecurity analyst, VPN is critical for a number of reasons; privacy, secure communications, IP Masking, Restrictions bypasses, No-log policy, Data encryption etc. 

Before downloading and configuring, you must have created an account with Windscribe on their [official website](https://windscribe.com/signup), ensure your mail is verified so as to be given more GB, and to avoid potential issues with your account.

`sudo apt update && sudo apt upgrade -y` >> updates the entire virtual machine

On their [official website](https://windscribe.com/), at the top right, click on download. Ensure you download the version compatible with your PC, windows, linux or mac.
Using the terminal, navigate to the "Downloads" folder >>

`dpkg --install windscribe_2.12.7_amd64.deb` >> installs windscribe on the VM

`sudo apt install libxcb-cursor0 libxcb-util1 libc6 libcap2 libdbus-1-3 libexpat1 libfontconfig1 libfreetype6 libgcc-s1 libgdk-pixbuf-2.0-0 libglib2.0-0 libgtk-3-0 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxtst6` >> *Installs all dependencies required for Windscribe to download and function*

`sudo apt --fix-broken install` >> *installs additional missing dependencies* 

`sudo systemctl start windscribe-helper` >> *indicates that systemd service was set-up*

`ls /opt/windscribe` >> *checks through if "windscribe-CLI" is running*

`/opt/windscribe/windscribe-cli --help` >> *executes and specifies windscribe's full path. IF THIS WORKS SMOOTHLY*

 `windscribe-cli --version` >> *verifies windscribe is configured perfectly on the machine + it displays relevant commands useful for windscribe*

`windscribe-cli login "username" "password"` >> *input your windscribe login details to connect and power on windscribe VPN*

`windscribe-cli status` >> *check connection status*



 <img src="Screenshot from 2025-01-17 05-57-36.PNG" alt="alt text" width="750">



 #### **TROUBLESHOOTING; Complications might present itself while installing all dependencies depending on system OS or login issues, ensure to install correctly and it won't take longer time.**