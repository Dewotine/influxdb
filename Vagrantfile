# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
	
	config.ssh.insert_key = false
	
	config.vm.define "icingamaster" do |icingamaster|
  	icingamaster.vm.box = "debian/jessie64"
	icingamaster.vm.network "public_network", ip: "192.168.1.200", bridge: "eth0"
	icingamaster.vm.hostname = "icingamaster"
  	icingamaster.vm.network "forwarded_port", guest: 80, host: 8080
  	icingamaster.vm.network "forwarded_port", guest: 443, host: 8443
  	icingamaster.vm.network "forwarded_port", guest: 5432, host: 5432
	end

        config.vm.define "icingasat1" do  |icingasat1|
        icingasat1.vm.box = "debian/jessie64"
        icingasat1.vm.network "public_network", ip: "192.168.1.201", bridge: "eth0"
        icingasat1.vm.hostname = "icingasat1"
        icingasat1.vm.network "forwarded_port", guest: 80, host: 8081
        icingasat1.vm.network "forwarded_port", guest: 443, host: 8444
        icingasat1.vm.network "forwarded_port", guest: 5432, host: 5433
	icingasat1.vm.network "private_network", ip: "192.168.2.201"
        end

	config.vm.define "icingasat2" do  |icingasat2|
        icingasat2.vm.box = "debian/jessie64"
        icingasat2.vm.network "public_network", ip: "192.168.1.202", bridge: "eth0"
        icingasat2.vm.hostname = "icingasat2"
        icingasat2.vm.network "forwarded_port", guest: 80, host: 8082
        icingasat2.vm.network "forwarded_port", guest: 443, host: 8445
        icingasat2.vm.network "forwarded_port", guest: 5432, host: 5434
	icingasat2.vm.network "private_network", ip: "192.168.3.202"
        end

#config.vm.define "icingacli1" do  |icingacli1|
#       icingacli1.vm.box = "debian/jessie64"
#       icingacli1.vm.hostname = "icingacli1"
#icingacli1.vm.network "private_network", ip: "192.168.2.1"
#       end

#config.vm.define "icingacli2" do  |icingacli2|
#       icingacli2.vm.box = "debian/jessie64"
#       icingacli2.vm.hostname = "icingacli2"
#icingacli2.vm.network "private_network", ip: "192.168.3.1"
#       end


#	config.vm.define "dc12phc061" do  |centos_test|
#  	centos_test.vm.box = "centos/7"
#  	centos_test.vm.hostname = "dc12phc061"
#	centos_test.vm.network "public_network", ip: "192.168.1.202", bridge: "eth0"
#  	centos_test.vm.network "forwarded_port", guest: 80, host: 8082
#  	centos_test.vm.network "forwarded_port", guest: 443, host: 8445
#	end
#
#        config.vm.define "dc12phc041" do  |centos_test|
#        centos_test.vm.box = "centos/7"
#        centos_test.vm.hostname = "dc12phc041"
#        centos_test.vm.network "public_network", ip: "192.168.1.203", bridge: "eth0"
#        centos_test.vm.network "forwarded_port", guest: 80, host: 8083
#        centos_test.vm.network "forwarded_port", guest: 443, host: 8446
#        end

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

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

  # Define a Vagrant Push strategy for pushing to Atlas. Other push strategies
  # such as FTP and Heroku are also available. See the documentation at
  # https://docs.vagrantup.com/v2/push/atlas.html for more information.
  # config.push.define "atlas" do |push|
  #   push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
  # end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
