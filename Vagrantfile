# -*- mode: ruby -*-
# vi: set ft=ruby :
# vi: set tabstop=2 :
# vi: set shiftwidth=2 :

Vagrant.configure("2") do |config|

  vms = [
    { :box => "debian/jessie64",  :docker => "hanxhx/vagrant-ansible:debian8", :name => "debian-jessie",           :vars => { "nodejs_upstream": false }},
    { :box => "debian/jessie64",  :docker => "hanxhx/vagrant-ansible:debian8", :name => "debian-jessie-upstream",  :vars => { "nodejs_upstream": true  }},
    { :box => "debian/stretch64", :docker => "hanxhx/vagrant-ansible:debian9", :name => "debian-stretch",          :vars => { "nodejs_upstream": false }},
    { :box => "debian/stretch64", :docker => "hanxhx/vagrant-ansible:debian9", :name => "debian-stretch-upstream", :vars => { "nodejs_upstream": true  }}
  ]


  config.vm.provider "virtualbox" do |v|
    v.cpus = 1
    v.memory = 256
  end

  config.vm.network "private_network", type: "dhcp"

  vms.each do |opts|
		name = 'docker-' + opts[:name]
    config.vm.define name do |m|
      m.vm.provider "docker" do |d|
        d.image = opts[:docker]
        d.remains_running = true
        d.has_ssh = true
      end
      m.vm.provision "ansible" do |ansible|
        ansible.playbook = "tests/test.yml"
        ansible.verbose = 'vv'
        ansible.sudo = true
      end
    end
  end

  vms.each do |opts|
    config.vm.define opts[:name] do |m|
      m.vm.box = opts[:box]
      m.vm.network "private_network", type: "dhcp"
      m.vm.provision "ansible" do |ansible|
        ansible.playbook = "tests/test.yml"
        ansible.verbose = 'vv'
        ansible.sudo = true
        ansible.extra_vars = opts[:vars]
      end
    end
  end
end
