## Ubuntu zero configuration

Author: [timmson666@mail.ru](mailto:timmson666@mail.ru)

### Requirements

 * Ubuntu/Xubuntu x64 standard host image

### Install
```
sudo apt-add-repository ppa:ansible/ansible
sudo apt -y update && sudo apt -y install ansible git pip software-properties-common
```

### Launch
```
git clone https://github.com/timmson/ubuntu-zero-configuration.git
ansible-playbook -i "localhost," -c local site.yml
```


