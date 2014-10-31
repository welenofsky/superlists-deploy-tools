# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  #config.vm.provision :shell, :inline => "apt-get update"

  config.vm.box = "jwele/trusty64"

  config.vm.network :forwarded_port, guest: 80, host: 8080

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision.ansible.yaml"
    ansible.inventory_path = "ansible.inventory"
    ansible.limit = "local"
  end

end