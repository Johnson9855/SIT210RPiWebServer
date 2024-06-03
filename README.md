# SIT210RPiWebServer
SIT210 Project RPi Web Server using Jellyfin
User Manual:
1.	Format SD Card using SD Card Formatter and update the operating system with ‘sudo apt update’ and ‘sudo apt full-upgrade’.
2.	Install Package to access Jellyfin package with ‘sudo apt install apt-transport-https lsb-release’.
3.	Import GPG key with ‘curl https://repo.jellyfin.org/debian/jellyfin_team.gpg.key | gpg --dearmor | sudo tee /usr/share/keyrings/jellyfin-archive-keyring.gpg >/dev/null’
This key is important to help the repository remain secure.
4.	Add Jellyfin repository
‘echo "deb [signed-by=/usr/share/keyrings/jellyfin-archive-keyring.gpg arch=$( dpkg --print-architecture )] https://repo.jellyfin.org/debian $( lsb_release -c -s ) main" | sudo tee /etc/apt/sources.list.d/jellyfin.list’
5.	Update the package list with
‘sudo apt update’
So that the package manager will be aware of the changes.
6.	Use ‘sudo apt install jellyfin’ to install Jellyfin
7.	To access jellyfin, go to the web browser and enter 
http://[IPADDRESS]:8096
8.	Next, we will use the interface to set a username and password for the account.
9.	Put files from computer into the external hard drive, then plug the hard drive into the Raspberry Pi 3.
10.	The rest will be quite self-explanatory on the Jellyfin, as it is easy to navigate.
11.	For example, to create a new library in Jellyfin just navigate to dashboard > Libraries, then click on “Add new library”, select the type of media you want to add and choose the directory for the media in Raspberry Pi.
Permission issues
To access some directories that require permission, we need to give jellyfin permission.
1.	First, we need to enable superuser by using ‘sudo su’
2.	Then, run the commands ‘find [DIRECTORY] -type d -exec chmod 755 {}\;’ and ‘find [DIRECTORY -type f -exec chmod 644{} \;’
