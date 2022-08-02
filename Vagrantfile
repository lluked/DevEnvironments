Vagrant.configure("2") do |config|

  config.vm.provider "virtualbox" do |virtualbox|
    virtualbox.gui = true
    virtualbox.memory = 4096
    virtualbox.cpus = 1
  end

  config.vm.synced_folder ".", "/vagrant"

  config.vm.define "debian" do |debian|
    debian.vm.box = "generic/ubuntu2204"
    debian.vm.provider "virtualbox" do |virtualbox|
      virtualbox.name = "Ubuntu-Dev"
    end
  end

  config.vm.define "redhat" do |redhat|
    redhat.vm.box = "generic/centos9s"
    redhat.vm.provider "virtualbox" do |virtualbox|
      virtualbox.name = "RedHat-Dev"
    end
  end

  config.vm.provision :ansible_local do |ansible|
    ansible.playbook = "ansible/site.yml"
    ansible.config_file = "ansible/ansible.cfg"
  end

end
