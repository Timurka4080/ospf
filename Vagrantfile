Vagrant.configure(2) do |config|
    config.vm.box = "centos/7"
  
    config.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "provisioning/playbook.yml"
      ansible.sudo = "true"
    end
  
  
    config.vm.provider "virtualbox" do |v|
        v.memory = 256
    end
  
    config.vm.define "R1" do |r1|
        r1.vm.network "private_network", ip: "10.10.10.1", netmask:"255.255.255.252", virtualbox__intnet: "net1"
        r1.vm.network "private_network", ip: "10.10.10.5", netmask:"255.255.255.252", virtualbox__intnet: "net2"
        r1.vm.network "private_network", ip: "10.10.10.13",netmask:"255.255.255.252", virtualbox__intnet: "net4"
        r1.vm.hostname = "R1"
    end
  
    config.vm.define "R2" do |r2|
        r2.vm.network "private_network", ip: "10.10.10.2", netmask:"255.255.255.252", virtualbox__intnet: "net1"
        r2.vm.network "private_network", ip: "10.10.10.9", netmask:"255.255.255.252", virtualbox__intnet: "net3"
        r2.vm.hostname = "R2"
    end
  
    config.vm.define "R3" do |r3|
        r3.vm.network "private_network", ip: "10.10.10.10", netmask:"255.255.255.252", virtualbox__intnet: "net3"
        r3.vm.network "private_network", ip: "10.10.10.6", netmask:"255.255.255.252", virtualbox__intnet: "net2"
        r3.vm.network "private_network", ip: "10.10.10.17", netmask:"255.255.255.252", virtualbox__intnet: "net5"
        r3.vm.hostname = "R3"
    end
  
    config.vm.define "R4" do |r4|
        r4.vm.network "private_network", ip: "10.10.10.14", netmask:"255.255.255.252", virtualbox__intnet: "net4"
        r4.vm.network "private_network", ip: "10.10.10.18", netmask:"255.255.255.252", virtualbox__intnet: "net5"        
        r4.vm.hostname = "R4"
    end
  

  end