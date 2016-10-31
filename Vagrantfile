# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  
  config.vm.provider "virtualbox" do |v|
     v.memory = 2048
     v.cpus = 2
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.extra_vars = {
      "url" => ENV["url"],
      "token" => ENV["token"],
      "name" => ENV["name"],
    }
  end
end

