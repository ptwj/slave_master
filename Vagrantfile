# -*- mode: ruby -*-
# vi: set ft=ruby :
$script = <<SCRIPT
JMETER_VER=2.12

echo "installing java..."
sudo apt-get update
sudo apt-get -y install openjdk-7-jdk

echo "install curl..."
sudo apt-get -y install curl

echo "install jmeter..."
curl -L -O http://mirror.switch.ch/mirror/apache/dist//jmeter/binaries/apache-jmeter-$JMETER_VER.tgz && sudo tar xzf apache-jmeter-$JMETER_VER.tgz -C /opt
sudo chown -R vagrant /opt/apache-jmeter-2.12
SCRIPT

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_url = "https://vagrantcloud.com/ubuntu/boxes/trusty64"

  config.vm.network "private_network", type: "dhcp"
  config.vm.provision "shell", inline: $script
  config.vm.hostname = "trusty64"

  config.vm.define :n1
  config.vm.define :n2
  config.vm.define :n3

end
