## FIRST THING FIRST

This installation list is based on my preferences while trying out Elementary OS on my late 2008 macbook and is not a definitive procedure list. Feel free to use at your own peril.

I want to acknowledge that this document is largely influenced by suberb's elementaryOS [post](https://gist.github.com/suberb/4635a6c338f0f66b63c0f502859e5b42).

---

<br />

## WHILE IT'S STILL FRESH

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

### Installing Apps

- [x] **GParted**
```
GPARTED?
```

- [x] **GIT**
```
sudo apt-get install git
```

- [x] **VLC**
```
sudo apt install vlc
```

- [x] ~~**Google Chromium**~~
```
sudo apt install chromium-browser
```

- [x] **Firefox**
```
sudo apt install firefox
```

---

<br />

## OTHER APPS

<br />

- [x] **Atom** [atom.io](https://atom.io)
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

There is an issue when suspending and subsequently resuming the machine: after waking up, the screen is still black and the only way to continue is to manually force the machine to turn off.

This issue seems to be related to the Elementary's display manager and Nvidia drivers, since apparently it doesn't appear in Ubuntu (I have also tried Mint and Manjaro in the same machine and they both worked fine).

Elementary uses LightDM as their display manager, while Ubutntu uses GDM3. Thus, a solution is to install GDM3 on the machine, which will solve the suspend/resume issue, albeit it will ruin elementary's slick new Greeter.

I am using a late 2008 Macbook with the Nvidia GeForce 9400M, but [here](https://elementaryos.stackexchange.com/questions/20986/suspend-resume-issue) is another post with a similar machine with the same issue.

<br />

- [x] **Fixing the issue** According to this [post](https://askubuntu.com/questions/829108/what-is-gdm3-kdm-lightdm-how-to-install-and-remove-them)

* To install GNOME Display Manager (gdm3)
```
sudo apt-get install gdm3
```

* If you have multiple display managers installed, you can choose between them using:
```
sudo dpkg-reconfigure gdm3
```
or
```
sudo dpkg-reconfigure lightdm
```

* To check which display manager is currently being used, run this command:
```
cat /etc/X11/default-display-manager
```

<br />
