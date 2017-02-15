# -*- mode: ruby -*-
# vi: set ft=ruby :

### Set variables
#================================================================

hostname = "derek.slate.pantheon"
ip = "192.168.33.10"

#================================================================


Vagrant.configure("2") do |config|

    config.vm.box = "scotch/box"
    config.vm.network "private_network", ip: "#{ip}"
    config.vm.hostname = hostname
    config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"]

    # Update hosts (https://github.com/cogitatio/vagrant-hostsupdater)
    config.hostsupdater.aliases = ["www.#{hostname}.dev","#{hostname}.dev"]
    
    # Optional NFS. Make sure to remove other synced_folder line too
    #config.vm.synced_folder ".", "/var/www", :nfs => { :mount_options => ["dmode=777","fmode=666"] }

    # Fix for slow external network connections
    config.vm.provider :virtualbox do |vb|
        vb.customize ['modifyvm', :id, '--natdnshostresolver1', 'on']
        vb.customize ['modifyvm', :id, '--natdnsproxy1', 'on']
    end

end
