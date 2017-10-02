## Ubuntu zero configuration

Author: [timmson666@mail.ru](mailto:timmson666@mail.ru)

### Requirements

 * Ubuntu/Xubuntu x64 standard host image
 
### Available tags
 * windows (common and specific tasks)
 * desktop (common and client tasks)
 * laptop  (common, client and laptop-specific tasks)
 * server  (common and server tasks)

### Install (run as root)
```
#apt update && apt -y install software-properties-common aptitude apport
apt-add-repository -y ppa:ansible/ansible
apt update
apt -y install ansible git
```

### Launch
```
git clone https://github.com/timmson/ubuntu-zero-configuration.git && cd ubuntu-zero-configuration 
ansible-playbook -i "localhost," -c local site.yml --tags desktop
```



