# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.ssh.insert_key = false

  config.vm.synced_folder "./playbooks", "/vagrant_data"

  config.vm.define "vagrant1" do |vagrant1|
    vagrant1.vm.box = "ubuntu/trusty64"
    vagrant1.vm.network :private_network, ip: "10.0.2.15"
    vagrant1.vm.network "forwarded_port", guest: 22, host: 2222
    vagrant1.vm.network "forwarded_port", guest: 3000, host: 3000
    vagrant1.vm.network "forwarded_port", guest: 80, host: 8080
    vagrant1.vm.network "forwarded_port", guest: 443, host: 8443
  end

  config.vm.define "vagrant2" do |vagrant2|
    vagrant2.vm.box = "ubuntu/trusty64"
    vagrant2.vm.network :private_network, ip: "10.0.2.16"
    vagrant2.vm.network "forwarded_port", guest: 22, host: 2223
    vagrant2.vm.network "forwarded_port", guest: 80, host: 8081
    vagrant2.vm.network "forwarded_port", guest: 443, host: 8444
  end

  config.vm.define "vagrant3" do |vagrant3|
    vagrant3.vm.box = "ubuntu/trusty64"
    vagrant3.vm.network :private_network, ip: "10.0.2.17"
    vagrant3.vm.network "forwarded_port", guest: 22, host: 2224
    vagrant3.vm.network "forwarded_port", guest: 80, host: 8082
    vagrant3.vm.network "forwarded_port", guest: 443, host: 8445
  end

end
