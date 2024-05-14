Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  
  
  config.vm.define"master" do |master|
    master.vm.hostname="master"
    master.vm.box = "ubuntu/focal64"
    master.vm.network "forwarded_port", guest: 80, host: 5001, host_ip: "127.0.0.1"
    master.vm.network "private_network", ip: "192.168.10.20", type: "dhcp"
    master.vm.network "public_network"
  end

  config.vm.define"slave" do |slave|
    slave.vm.hostname="slave"
    slave.vm.box = "ubuntu/focal64"
    slave.vm.network "forwarded_port", guest: 80, host: 5002, host_ip: "127.0.0.1"
    slave.vm.network "private_network", ip: "192.168.10.24", type: "dhcp"
    slave.vm.network "public_network"
  end 
end
