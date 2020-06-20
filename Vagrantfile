Vagrant.configure("2") do |config|
  # define an image / box (boxes at https://vagrantcloud.com/search.)
  config.vm.box = "centos/7"
  
  # set hostname
  config.vm.hostname = "docker-machine"
  
  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network
  config.vm.network "public_network", ip: "192.168.43.10"

  # Shared folder to the guest VM.
  # The first argument is the path on the host to the actual folder.
  # The second argument is the path on the guest to mount the folder.
  config.vm.synced_folder "data/", "/shared_data"


  config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
     vb.memory = "2048"
  end

  # shell commands to install docker CE
  config.vm.provision "shell", inline: <<-SHELL
  sudo -i
  
  yum install -y device-mapper-persistant-data lvm2 yum-utils
  
  yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
  
  yum install -y docker-ce docker-ce-cli containred.io
  
  systemctl enable docker && systemctl start docker
  
  docker --version
  
  SHELL
end

