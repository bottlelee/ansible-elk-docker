# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "bento/ubuntu-16.04" # 16.04 LTS
  config.vm.hostname = "elk-docker"

  # Expose the nomad api and ui to the host
  config.vm.network "forwarded_port", guest: 4646, host: 4646, auto_correct: true
  config.vm.network "private_network", ip: "172.28.128.10"

  # Increase memory for Parallels Desktop
  config.vm.provider "parallels" do |p, o|
    p.memory = "1024"
  end

  # Increase memory for Virtualbox
  config.vm.provider "virtualbox" do |vb|
        vb.memory = "8192"
        vb.cpus = "4"
  end

  # Increase memory for VMware
  ["vmware_fusion", "vmware_workstation"].each do |p|
    config.vm.provider p do |v|
      v.vmx["memsize"] = "1024"
    end
  end
end
