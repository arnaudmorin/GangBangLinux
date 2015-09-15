# GangBangLinux - OpenBox desktop based on Ubuntu

## Installation

### Ubuntu Mini

At first, you must install Ubuntu Mini. You can use the following link to find the Ubuntu Mini ISO:

[https://help.ubuntu.com/community/Installation/MinimalCD](https://help.ubuntu.com/community/Installation/MinimalCD "Ubuntu Mini")

At the end, you will be ask to install subsequent software: do **not** select anything for now, or eventually SSH server, depending on your needs.

### Install dependencies

```bash
sudo apt-get install git vim software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
```

### Clone this repo

```bash
git clone https://github.com/arnaudmorin/GangBangLinux.git
```

### Run ansible playbook

```bash
cd GangBangLinux/
ansible-playbook -i hosts --ask-become-pass site.yml
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
