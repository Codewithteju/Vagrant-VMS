Vagrant.configure("2") do |config|
  
    # VM: web01 with Ubuntu 20.04
    config.vm.define "web01" do |web01|
      web01.vm.box = "ubuntu/focal64"  # Ubuntu 20.04 64-bit box
      web01.vm.hostname = "web01"  # Set hostname for the VM
      web01.vm.network "private_network", ip: "192.168.56.21"  # Assign a static private IP
     
    end
    
    # VM: web02 with Ubuntu 20.04
    config.vm.define "web02" do |web02|
      web02.vm.box = "ubuntu/focal64"  # Ubuntu 20.04 64-bit box
      web02.vm.hostname = "web02"  # Set hostname for the VM
      web02.vm.network "private_network", ip: "192.168.56.22"  # Assign a static private IP
      
    end
    
    # VM: db01 with CentOS 7
    config.vm.define "db01" do |db01|
      db01.vm.box = "eurolinux-vagrant/centos-stream-9"  # CentOS 7 box
      db01.vm.hostname = "db01"  # Set hostname for the VM
      db01.vm.network "private_network", ip: "192.168.56.33"  # Assign a static private IP
     
      db01.vm.provision "shell", inline: <<-SHELL
        yum install wget unzip mariadb-server -y
        systemctl start mariadb
        systemctl enable mariadb
      SHELL
    end
  end
  