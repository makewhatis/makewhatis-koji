# encoding: utf-8

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|

  config.vm.box = "fedora-17-x86_64-base"
  #config.vm.box_url = "file://Users/djohansen/vagrant/f17-1/fedora-17-x86-64-base.box"
  config.vm.host_name = "koji.makewhatis.com"
  config.ssh.forward_agent = true
  config.vm.share_folder "PuppetFiles", "/etc/puppet/files", "files"
  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "manifests"
    puppet.manifest_file = "site.pp"
    puppet.options = ["--fileserverconfig=/vagrant/fileserver.conf"]
    puppet.module_path = "modules"
  end

end
