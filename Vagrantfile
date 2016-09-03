Vagrant.require_version ">= 1.7.0"

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"

  # Disable the new default behavior introduced in Vagrant 1.7, to
  # ensure that all Vagrant machines will use the same SSH key pair.
  # See https://github.com/mitchellh/vagrant/issues/5005
  config.ssh.insert_key = false

  config.vm.network "forwarded_port", guest: 80, host: 80

  #config.vm.synced_folder "/Users/aleksandr.ivanov/Projects", "/project", id: "vagrant-root", :nfs => true
  config.vm.synced_folder "/Users/aleksandr.ivanov/Projects", "/project", 
  :mount_options => ["dmode=777", "fmode=666"]

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end
end