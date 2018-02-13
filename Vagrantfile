# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "private_network", ip: "192.168.22.11"
  config.disksize.size = "15GB"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "3100"
    vb.cpus = 1
  end

  config.vm.provision "shell" do |s|
  	s.inline = "apt-get install -y python"
  end
  
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
