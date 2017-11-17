Vagrant.configure("2") do |config|
  config.vm.box = "landregistry/centos"

  config.ssh.forward_agent = true
  config.vm.network "private_network", :ip => "172.16.42.44"
  config.vm.provision :shell, :path => 'provision.sh'

  config.vm.box_version = "0.7.1"
  
  config.vm.provider :virtualbox do |vb|
    vb.name = "nginx-build"
    vb.customize ['modifyvm', :id, '--memory', ENV['VM_MEMORY'] || 2048]
    vb.customize ['modifyvm', :id, '--natdnshostresolver1', 'on']
    vb.customize ['modifyvm', :id, '--natdnsproxy1', 'on']
    vb.customize ["modifyvm", :id, "--cpus", ENV['VM_CPUS'] || 2]
  end

end
