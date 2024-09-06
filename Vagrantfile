
Vagrant.configure("2") do |config|
  

  config.vm.define "db" do |db|
    db.vm.box = "centos/7"  
    db.vm.hostname = "db"
    db.vm.network "private_network", ip: "192.168.56.10"  
    db.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"  
    end
    db.vm.provision "shell" , inline: <<-SHELL
    yum install wget unzip mariadb-server -y
    hostnamectl set-hostname db01
    SHELL
  end

 
  config.vm.define "web01" do |web01|
    web01.vm.box = "ubuntu/focal64"  
    web01.vm.hostname = "web01"
    web01.vm.network "private_network", ip: "192.168.56.11"  
    web01.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"  
    end
  end

 
  config.vm.define "web02" do |web02|
    web02.vm.box = "ubuntu/focal64"  
    web02.vm.hostname = "web02"
    web02.vm.network "private_network", ip: "192.168.56.12"  
    web02.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"  
    end
  end

end
