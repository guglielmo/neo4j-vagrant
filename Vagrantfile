# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<SCRIPT
echo I am provisioning...
sudo wget -O - http://debian.neo4j.org/neotechnology.gpg.key | sudo apt-key add -
sudo echo 'deb http://debian.neo4j.org/repo stable/' | sudo tee --append /etc/apt/sources.list.d/neo4j.list
sudo apt-get update
sudo apt-get install neo4j
SCRIPT

Vagrant.configure('2') do |config|
  config.vm.box = 'ubuntu/trusty64'
  config.vm.box_check_update = true

  config.vm.provision 'shell', inline: $script
end
