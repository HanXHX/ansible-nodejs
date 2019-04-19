# -*- mode: ruby -*-
# vi: set ft=ruby :
# vi: set tabstop=2 :
# vi: set shiftwidth=2 :

Vagrant.configure("2") do |config|

  vms = [
    { :name => "debian-jessie",           :box => "debian/jessie64",  :vars => { "nodejs_upstream": false }},
    { :name => "debian-jessie-upstream",  :box => "debian/jessie64",  :vars => { "nodejs_upstream": true  }},
    { :name => "debian-stretch",          :box => "debian/stretch64", :vars => { "nodejs_upstream": false }},
    { :name => "debian-stretch-upstream", :box => "debian/stretch64", :vars => { "nodejs_upstream": true  }},
    { :name => "debian-buster",           :box => "debian/buster64",  :vars => { "nodejs_upstream": false }},
    { :name => "debian-buster-upstream",  :box => "debian/buster64",  :vars => { "nodejs_upstream": true  }},
	]

  conts = [
    { :name => "docker-debian-jessie",           :docker => "hanxhx/vagrant-ansible:debian8",  :vars => { "nodejs_upstream": false }},
    { :name => "docker-debian-jessie-upstream",  :docker => "hanxhx/vagrant-ansible:debian8",  :vars => { "nodejs_upstream": true  }},
    { :name => "docker-debian-stretch",          :docker => "hanxhx/vagrant-ansible:debian9",  :vars => { "nodejs_upstream": false }},
    { :name => "docker-debian-stretch-upstream", :docker => "hanxhx/vagrant-ansible:debian9",  :vars => { "nodejs_upstream": true  }},
    { :name => "docker-debian-buster",           :docker => "hanxhx/vagrant-ansible:debian10", :vars => { "nodejs_upstream": false }},
    { :name => "docker-debian-buster-upstream",  :docker => "hanxhx/vagrant-ansible:debian10", :vars => { "nodejs_upstream": true  }},
  ]


  config.vm.network "private_network", type: "dhcp"

  conts.each do |opts|
    config.vm.define opts[:name] do |m|
      m.vm.provider "docker" do |d|
        d.image = opts[:docker]
        d.remains_running = true
        d.has_ssh = true
      end
      m.vm.provision "ansible" do |ansible|
        ansible.playbook = "tests/test.yml"
        ansible.verbose = 'vv'
        ansible.become = true
        ansible.extra_vars = opts[:vars]
      end
    end
  end

  vms.each do |opts|
    config.vm.define opts[:name] do |m|
      m.vm.provider "virtualbox" do |v|
        v.cpus = 1
        v.memory = 256
      end
      m.vm.box = opts[:box]
      m.vm.network "private_network", type: "dhcp"
      m.vm.provision "ansible" do |ansible|
        ansible.playbook = "tests/test.yml"
        ansible.verbose = 'vv'
        ansible.become = true
        ansible.extra_vars = opts[:vars]
      end
    end
  end
end
