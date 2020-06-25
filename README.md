# Ubuntu zero configuration

## Requirements

 * Ubuntu/Xubuntu x64 standard host image (or Windows 10 Bash for --tags=wsl)
 
## Available tags
 * wsl (common and specific tasks)
 * desktop (common and client tasks)
 * laptop  (common, client and laptop-specific tasks)
 * server  (common and server tasks)

## Installation

### Local machine (host)
#### Install Git,Ansible
##### WSL (Windows Subsystem for Linux) 
 * [Intall WSL](https://docs.microsoft.com/en-US/windows/wsl/install-win10)

##### Linux
```
sudo apt-add-repository -y ppa:ansible/ansible
sudo apt update
sudo apt -y install ansible git
```
### Create user (if not exist)
```
useradd user -s /bin/bash -G sudo -md /home/user
sed -i.bkp -e 's/%sudo\s\+ALL=(ALL\(:ALL\)\?)\s\+ALL/%sudo ALL=NOPASSWD:ALL/g' /etc/sudoers
```

#### Launch
```
git clone https://github.com/timmson/ubuntu-zero-configuration.git && cd ubuntu-zero-configuration 
ansible-playbook -i "localhost," -c local site.yml --tags desktop -K
```

### Virtual machine via Vagrant / Virtualbox
#### Install Git,Vagrant,Virtualbox
##### Windows
 * [Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
 * [Installing Vagrant & VirtualBox](https://www.sitepoint.com/getting-started-vagrant-windows/)

##### Linux
```
sudo apt update
sudo apt -y install vagrant virtualbox git
```

#### Launch
```
git clone https://github.com/timmson/ubuntu-zero-configuration.git && cd ubuntu-zero-configuration 
vagrant up
```




