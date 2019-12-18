Vagrant.configure("2") do |config|
  config.vm.box_check_update = "false"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end
  
  config.vm.define "core" do |subconfig|
    subconfig.vm.box = "centos/7"
    subconfig.vm.hostname = "core"
    subconfig.vm.network :private_network, ip: "10.0.0.9"
    subconfig.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook="core.yml" 
    end
  end

  config.vm.define "asbr0" do |subconfig|
    subconfig.vm.box = "centos/7"
    subconfig.vm.hostname = "asbr0"
    subconfig.vm.network :private_network, ip: "10.0.0.10"
    subconfig.vm.network :private_network, ip: "10.0.1.10"
    subconfig.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook="asbr0.yml" 
    end
  end
  config.vm.define "asbr1" do |subconfig|
    subconfig.vm.box = "centos/7"
    subconfig.vm.hostname = "asbr1"
    subconfig.vm.network :private_network, ip: "10.0.0.11"
    subconfig.vm.network :private_network, ip: "10.0.1.11"
    subconfig.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook="asbr1.yml" 
    end
  end
  config.vm.define "pe0" do |subconfig|
    subconfig.vm.box = "centos/7"
    subconfig.vm.hostname = "pe0"
    subconfig.vm.network :private_network, ip: "10.0.1.20"
    subconfig.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook="pe0.yml" 
    end
  end
  config.vm.define "pe1" do |subconfig|
    subconfig.vm.box = "centos/7"
    subconfig.vm.hostname = "pe1"
    subconfig.vm.network :private_network, ip: "10.0.1.21"
    subconfig.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook="pe1.yml" 
    end
  end
end
