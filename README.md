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
```sh
sudo apt-add-repository -y ppa:ansible/ansible
sudo apt update
sudo apt -y install ansible git
```
### Create user (if not exist)
```sh
useradd user -s /bin/bash -G sudo -md /home/user
sed -i.bkp -e 's/%sudo\s\+ALL=(ALL\(:ALL\)\?)\s\+ALL/%sudo ALL=NOPASSWD:ALL/g' /etc/sudoers
```

#### Launch
```sh
git clone https://github.com/timmson/ubuntu-zero-configuration.git && cd ubuntu-zero-configuration 
ansible-playbook -i "localhost," -c local site.yml --tags desktop -K
```

### Virtual machine via Vagrant / Virtualbox
#### Install Git,Vagrant,Virtualbox
##### Windows
 * [Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
 * [Installing Vagrant & VirtualBox](https://www.sitepoint.com/getting-started-vagrant-windows/)

##### Linux
```sh
sudo apt update
sudo apt -y install vagrant virtualbox git
```

#### Launch
```sh
git clone https://github.com/timmson/ubuntu-zero-configuration.git && cd ubuntu-zero-configuration 
vagrant up
```

### Useful .bashrc update
https://askubuntu.com/questions/730754/how-do-i-show-the-git-branch-with-colours-in-bash-prompt

```sh
parse_git_branch() {
 git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
if [ "$color_prompt" = yes ]; then
 PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[01;31m\]$(parse_git_branch)\[\033[00m\]\$ '
else
 PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w$(parse_git_branch)\$ '
fi
```




