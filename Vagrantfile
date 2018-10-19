BOX_IMAGE = "ubuntu/xenial64"
node_COUNT = 2

Vagrant.configure("2") do |config|
  config.vm.define "master" do |master|
    master.vm.box = BOX_IMAGE
		master.vm.hostname = "master"

		master.vm.network :private_network, ip: "10.0.0.10"

		master.vm.provider "virtualbox" do |v|
			v.name = "master"
			v.memory = 2048
			v.cpus = 2
		end

  config.vm.provision "shell", path: "install-kubernetes.sh"
	end

  (1..node_COUNT).each do |i|
    config.vm.define "node#{i}" do |subconfig|
      subconfig.vm.box = BOX_IMAGE
      subconfig.vm.hostname = "node#{i}"
      subconfig.vm.network :private_network, ip: "10.0.0.#{i + 10}"

        subconfig.vm.provider "virtualbox" do |v|
          v.name = "node#{i}"
          v.memory = 2048
          v.cpus = 2
        end

        config.vm.provision "shell", path: "install-docker.sh"
        config.vm.provision "shell", path: "install-kubernetes.sh"
    end
  end

end
