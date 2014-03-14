# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

config.vm.define "centos" do |centos_config|

    centos_config.vm.box = "Centos64-p"
    centos_config.vm.host_name = "centos-project-open"

    centos_config.vm.network :forwarded_port, guest: 80, host: 8080
    centos_config.vm.network :forwarded_port, guest:8000, host: 8000 

    centos_config.vm.provision :puppet do |centos_puppet|
       centos_puppet.manifests_path = "manifests"
       centos_puppet.manifest_file  = "site.pp"
       centos_puppet.module_path    = "modules"
    end
  end
end