# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.disksize.size = '40GB'

  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 1
  end

  config.vm.provision "shell", inline: <<-SHELL
  	apt-get install -y python
  SHELL
  
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end

  config.vm.provision "shell", run: "always" do |s|
    s.inline = "service tomcat restart"
  end
    
end
