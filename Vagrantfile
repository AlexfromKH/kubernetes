Vagrant.configure("2") do |config|
  config.vm.define "master" do |master|
    master.vm.box = "ubuntu/xenial64"
		master.vm.hostname = "master"

		master.vm.network :private_network, ip: "192.168.56.100"

		master.vm.provider "virtualbox" do |v|
			v.name = "master"
			v.memory = 2048
			v.cpus = 2
		end

	config.vm.provision "shell", path: "install-docker.sh"
  config.vm.provision "shell", path: "install-kuberenetes.sh"
	end

  config.vm.define "node1" do |node1|
    node1.vm.box = "ubuntu/xenial64"
		node1.vm.hostname = "node1"

		node1.vm.network :private_network, ip: "192.168.56.101"

		node1.vm.provider "virtualbox" do |v|
			v.name = "node1"
      v.memory = 2048
      v.cpus = 2
		end

  config.vm.provision "shell", path: "install-docker.sh"
  config.vm.provision "shell", path: "install-kuberenetes.sh"
  end

  config.vm.define "node2" do |node2|
    node2.vm.box = "ubuntu/xenial64"
		node2.vm.hostname = "node2"

		node2.vm.network :private_network, ip: "192.168.56.102"

		node2.vm.provider "virtualbox" do |v|
			v.name = "node2"
      v.memory = 2048
      v.cpus = 2
		end

  config.vm.provision "shell", path: "install-docker.sh"
  config.vm.provision "shell", path: "install-kuberenetes.sh"
  end

end
