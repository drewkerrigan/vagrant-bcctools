# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.box_version = "20200225.0.0"
  config.vm.provision :shell, :privileged => false, :path => "scripts/install-bcc.sh"
  config.vm.boot_timeout = 600
end