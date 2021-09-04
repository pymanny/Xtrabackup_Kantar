# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  config.vm.define "control" do |control|
    control.vm.box = "ubuntu/bionic64"
    control.vm.network "private_network", ip: "192.168.33.10"
    control.vm.hostname = "control"
    control.vm.synced_folder ".", "/vagrant", type: "nfs"
    control.vm.provider "virtualbox" do |vb|
#      vb.gui = true
     vb.customize ["modifyvm", :id, "--name", "control"]
     vb.memory = "1024"
    end
    control.vm.provision "shell", inline: <<-SHELL
      sudo apt update -y
      sudo apt install software-properties-common -y
      sudo add-apt-repository --yes --update ppa:ansible/ansible -y
      sudo apt install ansible -y
    SHELL
  end

    config.vm.define "db1" do |db1|
      db1.vm.box = "ubuntu/bionic64"
      db1.vm.network "private_network", ip: "192.168.33.11"
      db1.vm.hostname = "db1"
      db1.vm.synced_folder ".", "/vagrant", type: "nfs"
      db1.vm.provider "virtualbox" do |vb|
#      vb.gui = true
       vb.customize ["modifyvm", :id, "--name", "db1"]
       vb.memory = "1024"
       end
    end

    config.vm.define "db2" do |db2|
      db2.vm.box = "ubuntu/bionic64"
      db2.vm.network "private_network", ip: "192.168.33.12"
      db2.vm.hostname = "db2"
      db2.vm.synced_folder ".", "/vagrant", type: "nfs"
      db2.vm.provider "virtualbox" do |vb|
#      vb.gui = true
       vb.customize ["modifyvm", :id, "--name", "db2"]
       vb.memory = "1024"
       end
    end
end
