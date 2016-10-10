# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.synced_folder "~/workspace", "/home/vagrant/workspace", create: true
  config.vm.synced_folder ".", "/vagrant"
  config.vm.provision "shell", :path => "provision.sh"
end
