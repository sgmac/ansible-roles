# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  # config.vm.box = "centos/7"
  # config.vm.box = "debian/jessie64"
  config.vm.hostname = "ansiblelab"
  config.vm.network "private_network", ip: "192.168.60.60"


  config.vm.provider "virtualbox" do |v|
     v.name = "ansible"
  end

  config.vm.provision "shell", inline: "apt-get install python -y"
  # config.vm.provision "shell", inline: "yum install python -y"


  config.vm.provision "ansible" do |ansible|
	  ansible.playbook = "site.yaml"
	  # ansible.verbose = "-vvv"
  end
end
