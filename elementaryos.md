## FIRST THING FIRST

<br />

- [x] **Update OS**
```
sudo apt-get update
sudo apt-get upgrade
```

<br />

- [x] **Uninstall Apps**
```
sudo apt purge epiphany-browser epiphany-browser-data
sudo apt purge pantheon-mail
sudo apt purge noise
sudo apt purge audience
```

<br />

- [x] **Clean Up OS**
```
sudo apt autoremove -y
sudo apt autoclean -y
```

---

<br />

## TERMINAL STUFF

<br />

- [x] **Enable PPA (Properties Commons) & Ubuntu extras**
```
sudo apt install software-properties-common
sudo apt install ubuntu-restricted-extras
```

<br />

- [x] **Install Apps**
```
GPARTED?

# INSTALL GIT
sudo apt-get install git

# INSTALL VLC
sudo apt install vlc

# INSTALL CHROMIUM
sudo apt install chromium-browser

# INSTALL FIREFOX
sudo apt install firefox
```

---

<br />

## OTHER APPS

<br />

### Atom
- [x] [atom.io](https://atom.io)
* To install Atom on Debian, Ubuntu, or related distributions, add our official package repository to your system by running the following commands:
```
wget -qO - https://packagecloud.io/AtomEditor/atom/gpgkey | sudo apt-key add -
sudo sh -c 'echo "deb [arch=amd64] https://packagecloud.io/AtomEditor/atom/any/ any main" > /etc/apt/sources.list.d/atom.list'
sudo apt-get update
```
* You can now install Atom using apt-get (or apt on Ubuntu):
```
# Install Atom
sudo apt-get install atom
# Install Atom Beta
sudo apt-get install atom-beta
```
* Alternatively, you can download the Atom .deb package and install it directly:
```
# Install Atom
sudo dpkg -i atom-amd64.deb
# Install Atom's dependencies if they are missing
sudo apt-get -f install
```

---

<br />

## ELEMENTARY SUSPEND ISSUE WITH NVIDIA DRIVERS

<br />

Apparently there is an issue when suspending and subsequently resuming.
This issue seems to be related to LightDM since it doesn't happen on GDM3.
LightDM is the Elementary OS display manager, while GDM3 is Ubuntu's.


https://elementaryos.stackexchange.com/questions/20986/suspend-resume-issue


To install GNOME Display Manager (gdm3)
sudo apt-get install gdm3

If you have multiple display managers installed, you can choose between them using:
sudo dpkg-reconfigure gdm3
# or
sudo dpkg-reconfigure lightdm

To check which display manager is currently being used, run this command:
cat /etc/X11/default-display-manager
