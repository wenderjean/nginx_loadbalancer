VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

config.vm.box = "ubuntu-puppet"
config.vm.box_url = "http://files.vagrantup.com/precise32.box"

 config.vm.define :server1 do |server1_config|
   server1_config.vm.network :private_network, :ip => "192.168.33.10"
   server1_config.vm.provision "puppet" do |puppet|
     puppet.manifest_file = "config.pp"
   end
 end
 config.vm.define :server2 do |server2_config|
   server2_config.vm.network :private_network, :ip => "192.168.33.11"
   server2_config.vm.provision "puppet" do |puppet|
     puppet.manifest_file = "config.pp"
   end
 end
 config.vm.define :server3 do |server3_config|
   server3_config.vm.network :private_network, :ip => "192.168.33.12"
   server3_config.vm.provision "puppet" do |puppet|
     puppet.manifest_file = "config.pp"
   end
 end
 config.vm.define :server4 do |server4_config|
   server4_config.vm.network :private_network, :ip => "192.168.33.13"
   server4_config.vm.provision "puppet" do |puppet|
     puppet.manifest_file = "nginx.pp"
   end
 end
 config.vm.define :db do |db_config|
   db_config.vm.network :private_network, :ip => "192.168.33.14"
   db_config.vm.provision "puppet" do |puppet|
     puppet.manifest_file = "db.pp"
   end
 end

# config.vm.network :forwarded_port, guest: 3000, host: 3000
# config.vm.network :forwarded_port, guest: 3000, host: 3000
 
 config.vm.provider :virtualbox do |vb|
   vb.customize ["modifyvm", :id, "--memory", "1024", "--hwvirtex", "off"]
 end
end
