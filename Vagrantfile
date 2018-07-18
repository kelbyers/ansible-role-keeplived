# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define :c7 do |c|
    c.vm.box = "puppetlabs/centos-7.2-64-nocm"
    c.vm.hostname = "c7.dev"
    c.vm.network :private_network, :ip => '10.20.1.2'
  end

  config.vm.define :c6 do |c|
    c.vm.box = "puppetlabs/centos-6.6-64-nocm"
    c.vm.hostname = "c6.dev"
    c.vm.network :private_network, :ip => '10.20.1.3'
  end

  config.vm.define :cli do |c|
    c.vm.hostname = "cli.dev"
    c.vm.box = "puppetlabs/centos-7.2-64-nocm"
    c.vm.network :private_network, :ip => '10.20.1.4'
  end

  config.vm.provision :hosts do |p|
    p.autoconfigure = true
    p.sync_hosts = true
    p.add_host '10.20.1.254', ['gw.dev']
  end

end
