# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise64"
  
  config.vm.provider :vmware_fusion do |v|
    v.vmx["memsize"] = "512"
    v.vmx["numvcpus"] = "1"
  end

  config.vm.provision :shell, :inline => <<-SCRIPT
    export DEBIAN_FRONTEND nointeractive

    sudo apt-get update
    sudo apt-get upgrade -y

    sudo apt-get install -y python-software-properties
    sudo apt-get install -y man-db

    wget -qO- https://raw.github.com/progrium/dokku/master/bootstrap.sh | sudo bash
  SCRIPT
end
