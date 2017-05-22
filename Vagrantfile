# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/trusty64"

  config.vm.network "public_network"

   config.vm.provider "virtualbox" do |vb|
     vb.memory = "2048"
   end
  
   config.vm.provision "shell", inline: <<-SHELL
#     apt-get update
   SHELL

   config.vm.provision "ansible" do |ansible|
    ansible.playbook = 'kernel.yml'
    ansible.groups = {
      "default" => ["default"],
    }
   end

end
