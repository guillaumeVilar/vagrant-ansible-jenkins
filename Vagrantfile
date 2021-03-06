VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config| 
    config.vm.box = "geerlingguy/ubuntu1604" 
    config.vm.hostname = "jenkins.test"
    config.vm.network :private_network, ip: "192.168.76.76" 
    config.ssh.insert_key = false

    config.vm.provision 'shell', inline: 'echo "vagrant:vagrant" | chpasswd'
    config.vm.provision 'shell', inline: 'echo "root:root" | chpasswd'
    config.vm.provision "shell", inline: <<-SHELL
    sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/g' /etc/ssh/sshd_config
    systemctl restart sshd.service
    SHELL

    config.vm.provider :virtualbox do |v| 
        v.memory = 512
    end
end
