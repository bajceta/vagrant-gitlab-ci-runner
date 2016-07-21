# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  
  config.vm.provision "shell", inline: "sudo apt-get update -qq"
  config.vm.provision "shell", inline: "sudo apt-get install -qq python2.7"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.extra_vars = {
      "url" => ENV["url"],
      "token" => ENV["token"],
      "name" => ENV["name"],
    }
  end
end

