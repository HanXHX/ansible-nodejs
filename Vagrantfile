# -*- mode: ruby -*-
# vi: set ft=ruby :
# vi: set tabstop=2 :
# vi: set shiftwidth=2 :

Vagrant.configure("2") do |config|

  vms = [
    [ "debian-wheezy-upstream", "deb/wheezy-amd64", "192.168.39.29", "upstream" ],
    [ "debian-wheezy-debian",   "deb/wheezy-amd64", "192.168.39.29", "debian"   ],
    [ "debian-jessie-upstream", "deb/jessie-amd64", "192.168.39.31", "upstream" ],
    [ "debian-jessie-debian",   "deb/jessie-amd64", "192.168.39.32", "debian"   ]
  ]

  config.vm.provider "virtualbox" do |v|
    v.cpus = 1
    v.memory = 256
  end

  vms.each do |vm|
    config.vm.define vm[0] do |m|
      m.vm.box = vm[1]
      m.vm.network "private_network", ip: vm[2]

      m.vm.provision "ansible" do |ansible|
        ansible.playbook = "tests/test.yml"
        ansible.groups = { 
          vm[3] => vm[0] 
				}
        ansible.verbose = 'vv'
				ansible.sudo = true
      end
    end
  end
end
