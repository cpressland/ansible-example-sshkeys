Vagrant.configure("2") do |config|

  config.vm.define "customer1" do |c1|
    c1.vm.box = "bento/ubuntu-16.04"
    c1.vm.hostname = "customer1"

    c1.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", "1024"]
      v.customize ["modifyvm", :id, "--cpus", "2"]
      v.customize ["modifyvm", :id, "--name", "customer1"]
    end

    c1.vm.network :private_network, type: 'dhcp'
  end

  config.vm.define "customer2" do |c2|
    c2.vm.box = "bento/ubuntu-16.04"
    c2.vm.hostname = "customer2"

    c2.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", "1024"]
      v.customize ["modifyvm", :id, "--cpus", "2"]
      v.customize ["modifyvm", :id, "--name", "customer2"]
    end

    c2.vm.network :private_network, type: 'dhcp'
  end
end
