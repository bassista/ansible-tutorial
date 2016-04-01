# -a*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  #config.vm.network "forwarded_port", guest: 3000, host: 3000

  # config.vm.network "private_network", ip: "192.168.33.10"

  # config.vm.provider "virtualbox" do |vb|
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end

  $deployment = "deployment"
  $install = $deployment + "/install"

  ["install-ansible"].each do |script|
    config.vm.provision :shell do |sh|
      sh.name = script
      sh.path = $install + "/" + script + ".sh"
      sh.privileged = true
    end
  end
end
