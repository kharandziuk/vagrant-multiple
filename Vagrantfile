# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"


  config.vm.network "private_network", type: "dhcp"

  config.vm.define "server1" do |server1|
    server1.hosname = "server1"
  end

  config.vm.define "server2" do |server2|
    server2.hosname = "server2"
  end


end
