# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.define :dev do |dev_config|
    dev_config.vm.box = "precise64"
    dev_config.vm.box_url = "http://files.vagrantup.com/precise64.box"
    dev_config.vm.network :bridged

    dev_config.vm.provision :chef_solo do |chef|
      chef.cookbooks_path = ["cookbooks"]
      chef.add_recipe "apt"
      chef.add_recipe "build-essential"
      chef.add_recipe "rbenv:vagrant"
      chef.add_recipe "rbenv::system"
      chef.add_recipe "git"
    end
  end
end


