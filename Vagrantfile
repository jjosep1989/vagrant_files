# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.define :development do |development|
    development.vm.network :private_network, ip: "10.0.0.11"
    development.vm.hostname = "development"
    development.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.memory = "1500"
      vb.cpus = 2      
    end
  end
  
  config.vm.define :installer do |installer|
    installer.vm.network :private_network, ip: "10.0.0.10"
    installer.vm.hostname = "installer"
    installer.vm.provision "file", source: "./.vagrant/machines/development/virtualbox/private_key", destination: "/home/vagrant/private_key"
    installer.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.memory = "500"
      vb.cpus = 1     
    end
  end  


  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  
  config.vm.box = "ubuntu/xenial64"

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
  #  config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  #  config.vm.provider "virtualbox" do |vb|
  #    # Display the VirtualBox GUI when booting the machine
  #    vb.gui = false
  #      # Customize the amount of memory on the VM:
  #    vb.memory = "1500"
  #    vb.cpus = 2      
  #  end
      
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
    # config.vm.provision "shell", inline: <<-SHELL
    # SHELL
   
    # If errors occur, try running "vagrant provision" manually
    # after "vagrant up"
    # config.vm.provision :docker
    # To use docker_compose as a provisioning tool, install
    # vagrant-docker-compose plugin first. It should also solve the
    # "The '' provisioner could not be found." error:
    # $ vagrant plugin install vagrant-docker-compose --> v1
    # config.vm.provision :"docker_compose"
   
   config.ssh.forward_agent = true
end
