# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "mmichal/ubuntu18_04"
  config.vm.network "private_network", ip: "192.168.123.123"

   config.vm.provider "virtualbox" do |vb|
     vb.gui = true
     vb.memory = "2048"
   end

  config.vm.provision "shell", inline: <<-SHELL
  
########################Jenkins & Java########################
  sudo apt update
  sudo apt install openjdk-8-jdk -y
  wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
  sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
  sudo apt update
  sudo apt install jenkins -y
  systemctl status jenkins
  echo "Setup Jenkins"
  sudo cp /vagrant/Configuration/Jenkins/config.xml /var/lib/jenkins/
  sudo mkdir -p /var/lib/jenkins/users/admin
  sudo cp /vagrant/Configuration/Jenkins/users/admin/config.xml /var/lib/jenkins/users/admin/
  sudo chown -R jenkins:jenkins /var/lib/jenkins/users/
########################Nginx########################
  echo "Installing nginx"
  sudo apt-get -y install nginx -y
  sudo systemctl start nginx
  echo "Configuring nginx"
  cd /etc/nginx/sites-available
  sudo rm default ../sites-enabled/default
  sudo cp /vagrant/Configuration/Nginx/jenkins.conf /etc/nginx/sites-available/
  sudo ln -s /etc/nginx/sites-available/jenkins.conf /etc/nginx/sites-enabled/jenkins
  sudo systemctl restart nginx
  sudo systemctl restart jenkins
  echo "Done"
  SHELL
end
