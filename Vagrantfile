Vagrant.configure("2") do |config|
    config.vm.provision "shell", path: "script.sh"

    config.vm.define "controle" do |controle|		
    	controle.vm.box = "shekeriev/debian-11"
        controle.vm.hostname = "controle"
    	controle.vm.network "private_network", ip: "192.168.58.10"
    	controle.vm.provider "virtualbox" do |vb|
            vb.memory = "2048" 
            vb.cpus = 2
            vb.name = "controle"
        end
	controle.vm.provision "ansible_local" do |ansible|
		ansible.playbook = "playbook.yml"
		ansible.install_mode = "pip"
	end

    end
     
    config.vm.define "web" do |web|		
    	web.vm.box = "shekeriev/debian-11"
        web.vm.hostname = "web"
    	web.vm.network "private_network", ip: "192.168.58.11"
    	web.vm.provider "virtualbox" do |vb|
            vb.memory = "512" 
            vb.cpus = 2
            vb.name = "web"
        end
    end

    config.vm.define "db" do |db|		
    	db.vm.box = "shekeriev/debian-11"
        db.vm.hostname = "db"
    	db.vm.network "private_network", ip: "192.168.58.12"
    	db.vm.provider "virtualbox" do |vb|
            vb.memory = "512" 
            vb.cpus = 2
            vb.name = "db"
        end
    end

end

  
  
