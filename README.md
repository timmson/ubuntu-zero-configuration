# Ubuntu zero configuration
Author: [timmson666@mail.ru](mailto:timmson666@mail.ru)

## Requirements

 * Ubuntu/Xubuntu x64 standard host image (or Windows 10 Bash for --tags=windows)
 
## Available tags
 * windows (common and specific tasks)
 * desktop (common and client tasks)
 * laptop  (common, client and laptop-specific tasks)
 * server  (common and server tasks)

## Installation

### Local machine (host)
#### Install Git,Ansible
##### Windows
 * [Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
 * [Ansible on Windows](http://www.tomsitpro.com/articles/how-to-use-ansible-on-windows,1-3479.html) 

##### Linux
```
sudo apt-add-repository -y ppa:ansible/ansible
sudo apt update
sudo apt -y install ansible git
```
### Create user (if not exist)
```
useradd user -s /bin/bash -G sudo -md /home/user && sed -i.bkp -e 's/%sudo\s\+ALL=(ALL\(:ALL\)\?)\s\+ALL/%sudo ALL=NOPASSWD:ALL/g' /etc/sudoers
```

#### Launch
```
git clone https://github.com/timmson/ubuntu-zero-configuration.git && cd ubuntu-zero-configuration 
ansible-playbook -i "localhost," -c local site.yml --tags desktop
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




