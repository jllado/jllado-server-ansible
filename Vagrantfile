Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64" #Ubuntu boxes https://app.vagrantup.com/ubuntu
  config.disksize.size = '30GB'  #vagrant plugin install vagrant-disksize
  config.vm.provision "shell", inline: "adduser --disabled-password --gecos '' jllado; true"
  config.vm.provision "shell", inline: "apt update -y --fix-missing"
  config.vm.provision "shell", inline: "apt install ubuntu-gnome-desktop -y --fix-missing"
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "jllado_server_playbook.yml"
  end
end
