- Asterisk-FreePBX-A2Billing

- Bundle installer for Asterisk, FreePBX, A2Billing in Debian based distros.

- Tested on Debian 8 - x86 & x64 using Vmware 11.

1. Installation

apt-get update

apt-get -y upgrade

apt-get -y install dos2unix

cd ~/

wget https://github.com/P00/Asterisk-FreePBX-A2Billing/blob/master/installer.sh

dos2unix installer.sh

chmod +x installer.sh

./installer.sh

- Note: If you are using VMware and want to install the VMware-additions before anything else you need to install the
following dependencies first to be able to compile the kernel.

apt-get -y install gcc make linux-headers-$(`uname` -r)

1. Mysql database configuration for Asterisk & FreePBX

- During Mysql package installation you will be asked to enter the password for the root account. VERY IMPORTANT you need to enter pbx4fun as the password. Do not change it to something else or you will find out sooner or later that things will not work as intended.

- During the installation process you will prompted to enter the Database info for Asterisk. If there is a value 
already set between [] just press enter and continue. When asked for the database password type pbx4fun

1. Mysql database configuration for A2BIlling

- You will be asked to enter A2Billing database info, please enter the following

Database  = a2billing_db

Hostname = 127.0.0.1      # Note: mysql will only allow local connections unless you change mysql config file.

User = root

passord = pbx4fun

1. Miscellaneous

- During the installtion process of Asterisk you will be presented with a menu. If you would like to have music on holdyou need to make sure to enable it there, save changes and exit the menu to continue.

- During the installation process of Astersik you will prompted to enter your country code, if you are no sure which one its, google it.

- When installing google voice module in Asterisk 13 you need to add two .so files to the loaded modules 
example: (mogit.so), you will see a module not loaded error when trying to setup the google voice trunk and it will
tell you the names of the two modules that needs to be loaded. Reboot and you are goo to go.

- If the script is not of your liking feel free to modify it to your needs, this is a basic installer to integrate
all 3 applications together using a single installer with the less possible user interaction.

1. Login to FreePBX & A2Billing

FreePBX = http://yourlocalip/  - Note: You will be asked to create an username and password for the admin role

A2billing = http://yourlocalip/a2billing/admin

user = root

password = changepassword

- If you need help with A2Billing please google it, there is plenty of forums willing to help anyone who ask for help.
You need to configure A2billing and FreePBX to work together properly no futher configuration is done by the  installer.

