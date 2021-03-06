# vagrant-ansible-jenkins
Deployment of Jenkins on a VirtualBox Ubuntu VM using Vagrant and an Ansible playbook. 

Example of a vagrant VM deployment (with enabling root ssh and password), and 
ansible playbook associated in order to install Jenkins on the VM.

Can be used in order to do Jenkins tests locally or be extended to test other distribution / playbooks. 

This example is based on the example Jenkins CI of the book 'Ansible For DevOps'. I modified the example to: 
* make it work on MacOS, and 
* dissociated Vagrant provisioning and Ansible playbook.

Tested with the following versions: 
* Ansible 2.10.5
* Vagrant 2.2.7
* VirtualBox 6.0.12
* macOS Catalina 10.15.7

# Prerequisite: 
* Ansible
* Ansible galaxy
* Vagrant
* VirtualBox

# Installation: 
```
ansible-galaxy install -r requirements.yml
vagrant up
ansible-playbook -i inventory.yml provision.yml
```

We should have the Jenkins GUI available when visiting http://192.168.76.76:8080

![Screenshot](screenshot.png)

