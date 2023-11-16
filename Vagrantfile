Vagrant.configure("2") do |config|
  config.vm.define "mong-node01" do |node|
    node.vm.box = "ubuntu/focal64"
    node.vm.hostname = "mong-node01"
    node.vm.network "private_network", ip: "172.16.0.10"
    node.vm.provider "virtualbox" do |v|
      v.name = "mong-node01"
      v.memory = 4096  # 4GB RAM
      v.cpus = 2       # 2 CPUs
    end
    node.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y gnupg
      wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
      echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
      sudo apt-get update
      sudo apt-get install -y mongodb-org
      sudo sed -i '/bindIp/s/^#//g' /etc/mongod.conf
      sudo systemctl restart mongod
      sudo hostnamectl set-hostname mong-node01
      echo "172.16.0.10 mong-node01" | sudo tee -a /etc/hosts
      echo "172.16.0.20 mong-node02" | sudo tee -a /etc/hosts
      echo "172.16.0.30 mong-node03" | sudo tee -a /etc/hosts
    SHELL
  end

  config.vm.define "mong-node02" do |node|
    node.vm.box = "ubuntu/focal64"
    node.vm.hostname = "mong-node02"
    node.vm.network "private_network", ip: "172.16.0.20"
    node.vm.provider "virtualbox" do |v|
      v.name = "mong-node02"
      v.memory = 4096  # 4GB RAM
      v.cpus = 2       # 2 CPUs
    end
    node.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y gnupg
      wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
      echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
      sudo apt-get update
      sudo apt-get install -y mongodb-org
      sudo sed -i '/bindIp/s/^#//g' /etc/mongod.conf
      sudo systemctl restart mongod
      sudo hostnamectl set-hostname mong-node02
      echo "172.16.0.10 mong-node01" | sudo tee -a /etc/hosts
      echo "172.16.0.20 mong-node02" | sudo tee -a /etc/hosts
      echo "172.16.0.30 mong-node03" | sudo tee -a /etc/hosts
    SHELL
  end

  config.vm.define "mong-node03" do |node|
    node.vm.box = "ubuntu/focal64"
    node.vm.hostname = "mong-node03"
    node.vm.network "private_network", ip: "172.16.0.30"
    node.vm.provider "virtualbox" do |v|
      v.name = "mong-node03"
      v.memory = 4096  # 4GB RAM
      v.cpus = 2       # 2 CPUs
    end
    node.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y gnupg
      wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
      echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
      sudo apt-get update
      sudo apt-get install -y mongodb-org
      sudo sed -i '/bindIp/s/^#//g' /etc/mongod.conf
      sudo systemctl restart mongod
      sudo hostnamectl set-hostname mong-node03
      echo "172.16.0.10 mong-node01" | sudo tee -a /etc/hosts
      echo "172.16.0.20 mong-node02" | sudo tee -a /etc/hosts
      echo "172.16.0.30 mong-node03" | sudo tee -a /etc/hosts
    SHELL
  end
end