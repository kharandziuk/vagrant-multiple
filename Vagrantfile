# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.network "private_network", type: "dhcp"

  # show ip in the console
  config.vm.provision "shell", inline: "hostname -I | cut -d' ' -f2"

  config.vm.define "server1" do |server1|
    server1.vm.hostname = "server1"
    server1.vm.provision 'ansible' do |ansible|
      ansible.playbook = "playbook.yml"
      # run a particular task with e.g. $ START_TASK="task name" vagrant provision
      ansible.start_at_task=ENV['START_TASK']
      ansible.extra_vars = {
        port: 1500
      }
    end
  end

  config.vm.define "server2" do |server2|
    server2.vm.hostname = "server2"
  end


end
