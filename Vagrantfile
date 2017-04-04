Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox"
  config.vm.box = "bento/ubuntu-16.10"
  config.vm.provision "docker" do |d|
    d.pull_images "frapsoft/nikto"
    d.pull_images "sonarqube"
  end
  config.vm.network "public_network"
  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"
  config.vm.network "forwarded_port", guest: 9000, host: 9000
  config.vm.network "forwarded_port", guest: 9092, host: 9092
  config.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 2
  end
end
