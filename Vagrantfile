# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "neuland/debian-jessie-amd64"
  config.vm.network :forwarded_port, host: 8080, guest: 80

  config.vm.provision :shell, path: "provision.sh"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "frontend.yml"
    ansible.groups = {
        "vagrant" => ["default"]
    }
  end
end
