Personal DevOps configuration on Elementary OS / Ubuntu-like Linux distros
(Tested on Bionic)

Quick start from fresh image:
```bash
sudo apt-get update \
sudo apt-get -y install software-properties-common git \
sudo apt-add-repository --yes --update ppa:ansible/ansible \
sudo apt-get -y install ansible \
ansible-galaxy install -r requirements.yml
ansible-playbook playbook.yml --ask-become-pass
chsh -s /bin/zsh # from user, not root
# log out/in is be required for non-root docker ps
```
Manual install steps for VirtualBox
```bash
deb [arch=amd64] https://download.virtualbox.org/virtualbox/debian bionic contrib # add to /etc/apt/sources.list
wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
sudo apt-get update
sudo apt-get install virtualbox-6.0
```

If this an existing system with git and Ansible installed:
```bash
ansible-galaxy install -r requirements.yml
ansible-playbook playbook.yml --ask-become-pass
```
