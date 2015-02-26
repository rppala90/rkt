Vagrant.configure('2') do |config|
    # grab Ubuntu 14.04 official image
    config.vm.box = "ubuntu/trusty64" # Ubuntu 14.04

    # fix issues with slow dns https://www.virtualbox.org/ticket/13002
    config.vm.provider :virtualbox do |vb, override|
        vb.customize ["modifyvm", :id, "--natdnsproxy1", "off"]
    end

    # install Build Dependencies (GOLANG)
    config.vm.provision :shell, :privileged => false, :path => "scripts/install-go.sh"

    # Install Rocket
    config.vm.provision :shell, :privileged => false, :path => "scripts/install-rocket.sh"
end
