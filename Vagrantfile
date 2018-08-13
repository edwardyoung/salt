# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

# Build a 2 site Splunk infrastructure
# What hosts do I need? - 11 hosts???
# Salt master
# 1 deployer
# 4 search heads
# 1 master, deployer, license master
# 4 indexers
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.define "salt_master" do |salt_master|
    salt_master.vm.box = "bento/debian-9.5"
    salt_master.vm.hostname = "salt-master"
    salt_master.vm.network "private_network", ip: "192.168.50.2"
    salt_master.vm.network "forwarded_port", guest: 22, host: 2222
  end

  config.vm.define "splunk_deployer" do |splunk_deployer|
    splunk_deployer.vm.box = "bento/debian-9.5"
    splunk_deployer.vm.hostname = "spl-deployer"
    splunk_deployer.vm.network "private_network", ip: "192.168.50.3"
    splunk_deployer.vm.network "forwarded_port", guest: 22, host: 2223
  end

  config.vm.define "splunk_sh1" do |splunk_sh1|
    splunk_sh1.vm.box = "bento/debian-9.5"
    splunk_sh1.vm.hostname = "spl-sh1"
    splunk_sh1.vm.network "private_network", ip: "192.168.50.4"
    splunk_sh1.vm.network "forwarded_port", guest: 22, host: 2224
  end

  config.vm.define "splunk_sh2" do |splunk_sh2|
    splunk_sh2.vm.box = "bento/debian-9.5"
    splunk_sh2.vm.hostname = "spl-sh2"
    splunk_sh2.vm.network "private_network", ip: "192.168.50.5"
    splunk_sh2.vm.network "forwarded_port", guest: 22, host: 2225
  end

  config.vm.define "splunk_sh3" do |splunk_sh3|
    splunk_sh3.vm.box = "bento/debian-9.5"
    splunk_sh3.vm.hostname = "spl-sh3"
    splunk_sh3.vm.network "private_network", ip: "192.168.50.6"
    splunk_sh3.vm.network "forwarded_port", guest: 22, host: 2226
  end

  config.vm.define "splunk_sh4" do |splunk_sh4|
    splunk_sh4.vm.box = "bento/debian-9.5"
    splunk_sh4.vm.hostname = "spl-sh4"
    splunk_sh4.vm.network "private_network", ip: "192.168.50.7"
    splunk_sh4.vm.network "forwarded_port", guest: 22, host: 2227
  end

  config.vm.define "splunk_master" do |splunk_master|
    splunk_master.vm.box = "bento/debian-9.5"
    splunk_master.vm.hostname = "spl-master"
    splunk_master.vm.network "private_network", ip: "192.168.50.8"
    splunk_master.vm.network "forwarded_port", guest: 22, host: 2228
  end

  config.vm.define "splunk_idx1" do |splunk_idx1|
    splunk_idx1.vm.box = "bento/debian-9.5"
    splunk_idx1.vm.hostname = "spl-idx1"
    splunk_idx1.vm.network "private_network", ip: "192.168.50.9"
    splunk_idx1.vm.network "forwarded_port", guest: 22, host: 2228
  end

  config.vm.define "splunk_idx2" do |splunk_idx2|
    splunk_idx2.vm.box = "bento/debian-9.5"
    splunk_idx2.vm.hostname = "spl-idx2"
    splunk_idx2.vm.network "private_network", ip: "192.168.50.10"
    splunk_idx2.vm.network "forwarded_port", guest: 22, host: 2229
  end

  config.vm.define "splunk_idx3" do |splunk_idx3|
    splunk_idx3.vm.box = "bento/debian-9.5"
    splunk_idx3.vm.hostname = "spl-idx3"
    splunk_idx3.vm.network "private_network", ip: "192.168.50.11"
    splunk_idx3.vm.network "forwarded_port", guest: 22, host: 2229
  end

  config.vm.define "splunk_idx4" do |splunk_idx4|
    splunk_idx4.vm.box = "bento/debian-9.5"
    splunk_idx4.vm.hostname = "spl-idx4"
    splunk_idx4.vm.network "private_network", ip: "192.168.50.12"
    splunk_idx4.vm.network "forwarded_port", guest: 22, host: 2230
  end

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"
  config.vm.synced_folder "../../Vagrant_Share", "/vagrant_splunk"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
