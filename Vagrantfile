# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Base Box
  # --------------------
  config.vm.box = "jessie64"
  config.vm.box_url = "http://dl.dropbox.com/s/1iif2jt13rnk5c5/jessie64.box"

  # Connect to IP
  # --------------------
  config.vm.network :private_network, ip: "192.168.0.101"

  # Forward to Port
  # --------------------
  #config.vm.network :forwarded_port, guest: 80, host: 8080

  config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"

  # Optional (Remove if desired)
  config.vm.provider :virtualbox do |v|
    # How much RAM to give the VM (in MB)
    # -----------------------------------
    v.customize ["modifyvm", :id, "--memory", "500"]

    # Uncomment the Bottom two lines to enable muli-core in the VM
    #v.customize ["modifyvm", :id, "--cpus", "2"]
    #v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  # Provisioning Script
  # --------------------
  # dummy.sh should be change by the file script that you want execute the first time
  # that you up the vagrant machine
  config.vm.provision "shell", path: "dummy.sh"

  # Synced Folder
  # --------------------
  config.vm.synced_folder ".", "/home/vagrant/Develop", :mount_options => [ "dmode=777", "fmode=666" ]
  #config.vm.synced_folder "./www", "/vagrant/www/", :mount_options => [ "dmode=775", "fmode=644" ], :owner => 'www-data', :group => 'www-data'

end