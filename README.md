
# Rtorrent + Rutorrent Auto Install Script for Ubuntu and Mint

## Manual install
These are Bash scripts to ease the installation of rtorrent, rutorrent + plugins.

Download the zip file version of this repo and set the extracted folder to you current directory.

`cd Downloads/Rtorrent-Auto-Install-master`

Make it executable. 

`sudo chmod +x rtorrent.auto.install-4.0.0-Ubuntu-16.04`

Run the script. 

`sudo ./rtorrent.auto.install-4.0.0-Ubuntu-16.04`
	
**That's it!**

Your rtorrent service is running and the Rutorrent web interface is at:

`localhost/rutorrent`
	
## Starting and Stopping Service

The script adds rtorrent as a systemd service. It will be automatically started when the script finishes. To manually start/stop:

`sudo systemctl start rtorrent`
    
`sudo systemctl stop rtorrent`
    
To enable start-up at boot: This is NOT set by default.

`sudo systemctl enable rtorrent`
    
##Versions

**Note:** This branch only maintains the Ubuntu/Mint version. For support for the Debian installs, please see the [master branch](https://github.com/Kerwood/Rtorrent-Auto-Install)

**Ubuntu 16.04**
This will work on the `systemd` versions of Ubuntu and Mint. It should be good on anything after Ubuntu 16.04 or Mint 18.0.

**Debian Wheezy**
The Wheezy script is of course developed for Wheezy but should run just fine on Ubuntu 13.04 and 14.04.

**Debian Jessie**
The Jessie script was adapted for the new default init system. Should run fine on systems that feature systemd (including Ubuntu 15.04+).

Please use `systemctl start rtorrent` and `systemctl stop rtorrent` instead of the service command.

**Raspbian Wheezy**
Credit for the Raspbian script goes to [miracle091](https://github.com/miracle091), good work mate.

**What the scripts do**
In the installation process you have to choose a system user to run rtorrent.
Also you will get the opportunity of installing a total of 46 plugins. See list further down.
The script add a init script that makes rtorrent start, at a possible reboot, in the
given username's screen/tmux session. Use "service rtorrent-init start" and
"service rtorrent-init stop" to start and stop rtorrent respectively.

Installs
--------

This scripts installs the following packages:

	apache2
	apache2-utils
	automake libtool
	build-essential
	curl
	git
	libapache2-mod-php5
	libapache2-mod-scgi
	libcppunit-dev
	libcurl4-openssl-dev
	libncurses5-dev
	libsigc++-2.0-dev
	libssl-dev
	openssl
	php5
	php5-cli
	php5-curl
	screen (tmux for Jessie/Ubuntu 15.04+)
	unrar-free
	unzip

The script compiles and installs lastest super-stable xmlrpc-c from sourceforge.
Installs rtorrent-0.9.6 and libtorrent-0.13.6 from github.
Install rutorrent-3.6 from novik65 official site.

**Plugins List**

- 1 - Erase Data Plugin
- 2 - Create Plugin
- 3 - Trafic Plugin
- 4 - RSS Plugin
- 5 - Edit Plugin
- 6 - Retrackers Plugin
- 7 - Throttle Plugin
- 8 - Cookies Plugin
- 9 - Scheduler Plugin
- 10 - Auto Tools Plugin
- 11 - Data Dir Plugin
- 12 - Track Lables Plugin
- 13 - Geo IP Plugin
- 14 - Ratio Plugin
- 15 - Show Peers like wTorrent Plugin
- 16 - Seeding Time Plugin
- 17 - HTTPRPC Plugin
- 18 - Diskspace Plugin
- 19 - Unpack Plugin
- 20 - Get Dir Plugin
- 21 - Source Plugin
- 22 - Chunks Plugin
- 23 - Data Plugin
- 24 - CPU Load Plugin
- 25 - Extsearch Plugin
- 26 - Theme Plugin
- 27 - Login Mgr Plugin
- 28 - ruTorrent Label Management Suite
- 29 - NFO Plugin
- 30 - Chat Plugin
- 31 - Logoff Plugin
- 32 - Pause Plugin
- 33 - Instant Search Plugin
- 34 - File Drop (FF > 3.6 & Chrome only).
- 35 - Check Port
- 36 - History
- 37 - iPad
- 38 - Extended Ratio
- 39 - Feeds
- 40 - Media Information
- 41 - RSS URL Rewrite
- 42 - Screenshot
- 43 - RPC
- 44 - Rutracker Check
- 45 - Noty
- 46 - Task
- 47 - All Plugins v3.6, More info at https://bintray.com/novik65/generic/ruTorrent


## Plugin Installation only

Exist a script that install only plugin, this is for the peoples then want to install some plugins instead to reinstall xmlrpc-c, libtorrent and rtorrent.

Actual version for the script: 
- **3.1**

Download the script. Remember to change the X.X to the actual version.

`wget https://raw.githubusercontent.com/Kerwood/rtorrent.auto.install/master/Plugins-installer-script-X.X   

Make it executable.

`chmod +x Plugins-installer-script-X.X`

Run the script.

`sudo ./Plugins-installer-script-X.X`


Login box does not appear after install!!!
-----------------------------------------

If the login box does not appear, it's probably because you have installed the all-plugins-pack or `httprpc` and/or `rpc` plugins is installed.
If one of these plugins are installed (they are both in the all-plugins-pack) you have two choise.

You can remove them using below command:

	sudo rm -rfv /var/www/rutorrent/plugins/{httprpc,rpc}
	
