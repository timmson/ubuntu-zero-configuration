# Ubuntu zero configuration
Author: [timmson666@mail.ru](mailto:timmson666@mail.ru)

## Requirements

 * Ubuntu/Xubuntu x64 standard host image
 
## Available tags
 * windows (common and specific tasks)
 * desktop (common and client tasks)
 * laptop  (common, client and laptop-specific tasks)
 * server  (common and server tasks)

## Installation

### Local machine (host)
#### Install Git,Ansible
```
sudo apt-add-repository -y ppa:ansible/ansible
sudo apt update
sudo apt -y install ansible git
```

#### Launch
```
git clone https://github.com/timmson/ubuntu-zero-configuration.git && cd ubuntu-zero-configuration 
ansible-playbook -i "localhost," -c local site.yml --tags desktop
```

### Virtual machine via Vagrant / Virtualbox
#### Install Git,Vagrant,Virtualbox
```
sudo apt update
sudo apt -y install vagrant virtualbox git
```

#### Launch
```
git clone https://github.com/timmson/ubuntu-zero-configuration.git && cd ubuntu-zero-configuration 
vagrant up
```




