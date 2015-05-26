# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Base Box
  # --------------------
  config.vm.box = "jessie64"
  config.vm.box_url = "http://dl.dropbox.com/s/1iif2jt13rnk5c5/jessie64.box"

  # Box updated
  # --------------------
  # config.vm.box_check_update = false

  # Forward to Port
  # --------------------
  config.vm.network "forwarded_port", guest: 8181, host: 8181

  # Connect to IP
  # --------------------
  config.vm.network "private_network", ip: "192.168.0.101"
  config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"

  # Synced Folder
  # --------------------
  config.vm.synced_folder ".", "/home/vagrant/Develop", mount_options: [ "dmode=777", "fmode=666" ]
  #config.vm.synced_folder "./www", "/vagrant/www/", :mount_options: [ "dmode=775", "fmode=644" ], "owner": 'www-data', "group": 'www-data'


  # Optional (Remove if desired)
  config.vm.provider "virtualbox" do |vb|
    # How much RAM to give the VM (in MB)
    # -----------------------------------
    vb.memory = "512"

    # Uncomment the Bottom two lines to enable muli-core in the VM
    #vb.gui = true
    #vb.cpus = "2"
    #vb.ioapic ="on"
  end

  # Provisioning Script
  # --------------------
  config.vm.provision "shell", inline: <<-SHELL
    export DEBIAN_FRONTEND=noninteractive
    sudo apt-get update
  SHELL
end
