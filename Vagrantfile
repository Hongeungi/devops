# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"
  config.vm.hostname = "ansible.local"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1024
  end
  if Vagrant.has_plugin?("vagrant-vbguest")
    config.vbguest.auto_update = false
  end
  
  config.vm.network "private_network", ip: "192.168.33.46"
  config.vm.synced_folder ".",  "/vagrant",  type: "rsync", rsync__exclude:  [".git/"]

  config.vm.provision "shell", inline: <<-SHELL
    export EDBIAN_FRONTEND=noninteractive
    sudo apt -y update
    sudo apt install -y software-properties-common
    sudo add-apt-repository --yes --update ppa:ansible/ansible
    sudo apt install -y ansible-core
  SHELL
end

