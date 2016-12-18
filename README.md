## Ubuntu zero configuration

Author: [timmson666@mail.ru](mailto:timmson666@mail.ru)

### Requirements

 * Ubuntu/Xubuntu x64 standard host image

### Install
```
sudo apt install software-properties-common && apt-add-repository ppa:ansible/ansible
sudo apt update && sudo apt install ansible git pip
```

### Launch
```
git clone https://github.com/timmson/ubuntu-zero-configuration.git
ansible-playbook -i "localhost," -c local site.yml
```


