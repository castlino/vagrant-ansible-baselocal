VAGRANT_API_VERSION = "2"

Vagrant.configure(VAGRANT_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

  # Change hostname, port and static-ip to suit your local environment.
  config.vm.hostname = 'ansible.lino'
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network :private_network, ip: "192.168.68.9"
  
  config.vm.provider "virtualbox" do |v|
      v.memory = 6192
      v.cpus = 4
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
