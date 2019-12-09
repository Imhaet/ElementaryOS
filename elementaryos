FIRST THING FIRST

Update OS
sudo apt update
sudo apt upgrade

Uninstall Apps
sudo apt purge epiphany-browser epiphany-browser-data
sudo apt purge pantheon-mail
sudo apt purge noise
sudo apt purge audience

Clean Up OS
sudo apt autoremove -y
sudo apt autoclean -y


TERMINAL STUFF

Enable PPA (Properties Commons)
sudo apt install software-properties-common
sudo apt install ubuntu-restricted-extras

Install Apps
sudo apt install vlc
# sudo apt install chromium-browser
sudo apt install firefox

Atom: atom.io
$ wget -qO - https://packagecloud.io/AtomEditor/atom/gpgkey | sudo apt-key add -
$ sudo sh -c 'echo "deb [arch=amd64] https://packagecloud.io/AtomEditor/atom/any/ any main" > /etc/apt/sources.list.d/atom.list'
$ sudo apt update
$ sudo apt install atom


ELEMENTARY SUSPEND ISSUE
Apparently there is an issue when suspending and subsequently resuming.
This issue seems to be related to LightDM since it doesn't happen on GDM3.
LightDM is the Elementary OS display manager, while GDM3 is Ubuntu's.

To install GNOME Display Manager (gdm3)
sudo apt-get install gdm3

If you have multiple display managers installed, you can choose between them using:
sudo dpkg-reconfigure gdm3
# or
sudo dpkg-reconfigure lightdm

To check which display manager is currently being used, run this command:
cat /etc/X11/default-display-manager
