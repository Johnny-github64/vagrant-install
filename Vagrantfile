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
  # boxes at https://vagrantcloud.com/search.
    config.vm.define "dbnginx" do |dbnginx|
        dbnginx.vm.box = "ubuntu/trusty64"
        dbnginx.vm.network "private_network", ip: "10.0.0.10"
        dbnginx.vm.provision "shell", path: "https://gist.githubusercontent.com/Johnny-github64/ab1be7fde0108ff33e4cc8259f504f0d/raw/b17e3ea0b44a0c13e83be7a144ce7a30c9329116/nginx%2520+%2520mysql%2520database%2520conf"
    end

    config.vm.define "lbserver1" do |lbserver1|
        lbserver1.vm.box = "ubuntu/trusty64"
        lbserver1.vm.network "private_network", ip: "10.0.0.11"
        lbserver1.vm.provision :shell do |shell|
        shell.args = "1"
        shell.path = "https://gist.githubusercontent.com/Johnny-github64/ae76042dd06d292483c9b08bc816ef5d/raw/0234ccc93d75f878d4790ee2628024188703879c/nginx%2520lb%2520conf"
        end
    end

    config.vm.define "lbserver2" do |lbserver2|
        lbserver2.vm.box = "ubuntu/trusty64"
        lbserver2.vm.network "private_network", ip: "10.0.0.12"
        lbserver2.vm.provision :shell do |shell|
        shell.args = "2"
        shell.path = "https://gist.githubusercontent.com/Johnny-github64/ae76042dd06d292483c9b08bc816ef5d/raw/0234ccc93d75f878d4790ee2628024188703879c/nginx%2520lb%2520conf"
        end
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
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
