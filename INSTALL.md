# GangBangLinux - OpenBox desktop based on Ubuntu

## Installation

### Ubuntu Mini

At first, you must install Ubuntu Mini. You can use the following link to find the Ubuntu Mini ISO:

[https://help.ubuntu.com/community/Installation/MinimalCD](https://help.ubuntu.com/community/Installation/MinimalCD "Ubuntu Mini")

At the end, you will be ask to install subsequent software: do **not** select anything for now, or eventually SSH server, depending on your needs.

### Install dependencies

```bash
sudo apt-get install git ansible
```

### Clone this repo

```bash
git clone https://github.com/arnaudmorin/GangBangLinux.git
```

### Run ansible playbook

```bash
cd GangBangLinux/

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
