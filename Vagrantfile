# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.ssh.forward_agent = true
  config.vm.box = "centos/7"
  config.vm.hostname = "hammock"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.synced_folder ".", "/vagrant", type: "rsync",
    rsync__args: ["--verbose", "--archive", "--delete", "--times", "-z"],
    rsync__exclude: [".git/", "vendor/"]
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ansible/site.yml"
    ansible.inventory_path = "ansible/hosts"
    ansible.limit = "vagrant"
  end
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 2
  end
end
