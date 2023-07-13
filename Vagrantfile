hosts = {
"kozha" => "192.168.2.3"
}
Vagrant.configure("2") do |config|
config.vm.box = "bento/ubuntu-20.04"
hosts.each do |name, ip|
config.vm.define name do |machine|
machine.vm.network :private_network, ip: ip
machine.vm.provider "virtualbox" do |v|
v.name = name
v.gui = false
v.memory = "4096"
v.cpus = 2
end
end
config.vm.provision "shell", path: "provision.sh"
end
end