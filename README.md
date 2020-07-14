# Vagrantbox Ubuntu 18.04 LTS and Jenkins
![GitHub issues](https://img.shields.io/github/issues/spy86/vagrant-jenkins) ![GitHub forks](https://img.shields.io/github/forks/spy86/vagrant-jenkins?style=social) ![GitHub stars](https://img.shields.io/github/stars/spy86/vagrant-jenkins?style=social) ![GitHub](https://img.shields.io/github/license/spy86/vagrant-jenkins) ![Twitter URL](https://img.shields.io/twitter/url?style=social&url=https%3A%2F%2Fgithub.com%2Fspy86%2Fvagrant-jenkins)



## Prerequisites
* Vagrant - https://releases.hashicorp.com/vagrant/2.2.9/vagrant_2.2.9_x86_64.msi
* Virtualbox - http://download.virtualbox.org/virtualbox/6.0.4/VirtualBox-6.0.4-128413-Win.exe

## How to use?

1. Clone https://github.com/spy86/vagrant-jenkins
2. Run `vagrant up` from terminal and wait while virtual machine is installed.
3. Add the following line to the hosts file `192.168.123.123 jenkins.local`
4. Open http://jenkins.local in web browser
5. Login: `admin` Password: `admin`