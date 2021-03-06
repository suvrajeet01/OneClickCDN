# OneClickCDN
A one-click shell script to set up a CDN node for your websites.

## What does this script do?
* Build Traffic Server from source.
* Add website to CDN
* Install SSL certificates
* One-click free SSL certificates from Let's Encrypt
* Manage websites, view stats, purge caches
* So on...

## System requirement
* Ubuntu 20.04 LTS 64 bit, Debian 10 64 bit (experimental), and CentOS 7/8 64 bit
* 1 IPv4
* At least 512 MB RAM for running CDN instance
* For the very first time, building the program from source requires about 1.5 GB RAM.  You may add SWAP to your VPS for this step.
* Root access, or sudo user

## How to use
* Firstly, you need to find a spare VPS with at least 1 IPv4, and install Ubuntu 20.04 LTS 64 bit (recommended) or Debian 10 64 bit OS.
* Then, please run the following command as a sudo user in SSH.
```
wget https://raw.githubusercontent.com/Har-Kuun/OneClickCDN/master/OneClickCDN.sh && sudo bash OneClickCDN.sh
```
* The script will guide you through the installation and configuration process.  You will also be prompted to add websites.
* In this process, you will be asked to set up SSL certificate.  You can choose to provide paths to your own SSL files (including private key, certificate, and CA chain certificate if applicable), or generate a free Let's Encrypt SSL certificate (not recommended, because if you have more than 1 CDN node, this will not work).  If you do choose to use the Let's Encrypt function, make sure to point your domain name to your CDN node IP BEFORE setting up the SSL.  You can always set up SSL later by selecting from the main menu.
* You can run the same script again in SSH in order to bring up the menu.  It will detect your current installation and will skip the installation process.
```
sudo bash OneClickCDN.sh
```
* If you make any changes, please make sure to exit the script by selecting the "0 - Save and quit script" option in the menu.  Changes will NOT be effective if you press Ctrl+C to quit the script.
* To uninstall the script and the Traffic Server, please run the following command in SSH.
```
wget https://raw.githubusercontent.com/Har-Kuun/OneClickCDN/master/uninstall.sh && sudo bash uninstall.sh
```

## Contact me
You can open an issue here if there is any problem/bug when you use it, or would like a new feature to be implemented.
For faster response, you can leave a message on this project webpage https://qing.su/article/oneclick-cdn.html

中文支持请访问 https://qing.su/article/oneclick-cdn.html

Thank you!

## Update log
* 07/19/2020        v0.0.1        Script created.
* 07/20/2020        v0.0.2        Add Debian 10 support; add systemd service.
* 07/21/2020        v0.0.3        Add CentOS 7/8 support; add a script to uninstall Traffic Server.
