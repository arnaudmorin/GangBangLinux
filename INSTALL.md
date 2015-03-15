# GangBangLinux - OpenBox desktop based on Ubuntu

## Installation

### Ubuntu Mini

At first, you must install Ubuntu Mini. You can use the following link to find the Ubuntu Mini ISO:

[https://help.ubuntu.com/community/Installation/MinimalCD](https://help.ubuntu.com/community/Installation/MinimalCD "Ubuntu Mini")

At the end, you will be ask to install subsequent software: do **not** select anything for now, or eventually SSH server, depending on your needs.

### Install base

#### Update your sources.list

```bash
sudo vi /etc/apt/sources.list
```

should contain:

```bash
deb http://fr.archive.ubuntu.com/ubuntu/ utopic main restricted universe multiverse
deb-src http://fr.archive.ubuntu.com/ubuntu/ utopic main restricted universe multiverse
deb http://fr.archive.ubuntu.com/ubuntu/ utopic-updates main restricted universe multiverse
deb-src http://fr.archive.ubuntu.com/ubuntu/ utopic-updates main restricted universe multiverse
deb http://fr.archive.ubuntu.com/ubuntu/ utopic-backports main restricted universe multiverse
deb-src http://fr.archive.ubuntu.com/ubuntu/ utopic-backports main restricted universe multiverse
deb http://security.ubuntu.com/ubuntu utopic-security main restricted universe multiverse
deb-src http://security.ubuntu.com/ubuntu utopic-security main restricted universe multiverse
deb http://archive.canonical.com/ubuntu utopic partner
deb-src http://archive.canonical.com/ubuntu utopic partner
deb http://extras.ubuntu.com/ubuntu utopic main
deb-src http://extras.ubuntu.com/ubuntu utopic main
```

#### Add PPA
Add this two PPA:

```bash
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:arnaud-morin/gangbang-linux
sudo add-apt-repository ppa:webupd8team/java
```

#### Update
Then update:

```bash
sudo apt-get update
```

#### Install packages
And install GangBangLinux base packages:

```bash
sudo apt-get install network-manager meld xscreensaver ssh file-roller gksu viewnior xfce4-screenshooter pavucontrol gstreamer1.0-plugins-bad xfburn libav-tools galculator evince libreoffice inkscape gparted unetbootin mbr arandr system-config-printer-gnome synaptic xfce4-battery-plugin xinit openbox xdm tint2 terminator git nitrogen pcmanfm geany vlc htop suckless-tools gimp chromium-browser firefox thunderbird gstreamer0.10-nice gstreamer0.10-plugins-base gstreamer0.10-plugins-good gstreamer0.10-x pidgin filezilla transmission gmrun lxappearance lxde-icon-theme xfce4-power-manager xfce4-notifyd xfce4-volumed conky cups language-pack-en language-pack-en-base language-pack-fr language-pack-fr-base language-pack-gnome-en language-pack-gnome-en-base language-pack-gnome-fr language-pack-gnome-fr-base obmenu oneko pnmixer xterm zenity oracle-java8-installer adobe-flashplugin vim
```

You must agree to the Oracle Java License.

### Clone GangBangLinux repo

Clone this git repo in **/usr/local/src/GangBangLinux**:

```bash
cd /usr/local/src/
sudo git clone https://github.com/arnaudmorin/GangBangLinux.git
sudo chown $USER:$USER GangBangLinux/ -R
```

### Install files

```bash
cp -r GangBangLinux/themes/ ~/.themes
cp -r GangBangLinux/config/ ~/.config
cp -r GangBangLinux/xscreensaver ~/.xscreensaver
sudo cp -r GangBangLinux/bin/* /usr/local/bin/
sudo chmod +x /usr/local/bin/*
```

### Create defaults home dir

```bash
mkdir ~/{downloads,documents,videos,images}
```

### Check network config
Comment out or remove any network configuration in /etc/network/interfaces, so that Network Manager handle the network instead of this file.

You should only have those lines:

```bash
# The loopback network interface
auto lo
iface lo inet loopback
```

### Reboot

```bash
sudo reboot
```
