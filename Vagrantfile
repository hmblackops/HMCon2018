# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"

  # # fix weird vagrant crap
  # config.ssh.username = "ubuntu"
  # config.ssh.password = "42407424ec0206a9be43f617"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.name = "HMCON-2018"
    vb.memory = "1024"
    vb.customize ["modifyvm", :id, "--usb", "on"]
    vb.customize ["modifyvm", :id, "--usbehci", "on"]
  end

  config.vm.provision "shell", inline: "apt install python -y"
  
  config.vm.provision "esp32", type: "ansible_local" do |ansible|
    # ansible.verbose = "v"
    ansible.playbook = "playbook.yml"
  end

end
