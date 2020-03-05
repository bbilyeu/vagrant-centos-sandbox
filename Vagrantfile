# -*- mode: ruby -*-
# vi: set ft=ruby :
# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
	config.vm.define "centos7" do |config|
			  config.vm.hostname = "centos7.xyzinc.com"
			  config.vm.box = "bento/centos-7.7"
			  
			  config.vm.synced_folder "~/Downloads", "/home/vagrant/Downloads"

			  config.vm.provision "shell",
				  inline: <<SCRIPT
echo 'password!' | sudo passwd -f --stdin root
sudo ssh-keygen -t rsa -N ""  -f  /home/vagrant/.ssh/id_rsa
SCRIPT

			  config.vm.provider "virtualbox" do |v|
				  v.customize [ "modifyvm", :id, "--cpus", "1" ]
				  v.customize [ "modifyvm", :id, "--memory", "1024" ]
				  v.customize [ "modifyvm", :id, "--cableconnected1", "on" ]
			  end

			  config.vm.network "private_network", ip: "192.168.200.70"
	  end
  
	config.vm.define "centos7-web" do |config|
			  config.vm.hostname = "centos7-web.xyzinc.com"
			  config.vm.box = "bento/centos-7.7"
			  
			  config.vm.synced_folder "~/Downloads", "/home/vagrant/Downloads"

			  config.vm.provision "shell",
				  inline: <<SCRIPT
echo 'password!' | sudo passwd -f --stdin root
sudo yum install -y httpd mariadb-server
sudo ssh-keygen -t rsa -N ""  -f  /home/vagrant/.ssh/id_rsa
SCRIPT

			  config.vm.provider "virtualbox" do |v|
				  v.customize [ "modifyvm", :id, "--cpus", "1" ]
				  v.customize [ "modifyvm", :id, "--memory", "1024" ]
				  v.customize [ "modifyvm", :id, "--cableconnected1", "on" ]
			  end

			  config.vm.network "private_network", ip: "192.168.200.71"
	  end
	  
	config.vm.define "centos7-ha" do |config|
			  config.vm.hostname = "centos7-ha.xyzinc.com"
			  config.vm.box = "bento/centos-7.7"
			  
			  config.vm.synced_folder "~/Downloads", "/home/vagrant/Downloads"

			  config.vm.provision "shell",
				  inline: <<SCRIPT
echo 'password!' | sudo passwd -f --stdin root
sudo yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
sudo yum install -y httpd mariadb-server varnish haproxy
sudo ssh-keygen -t rsa -N ""  -f  /home/vagrant/.ssh/id_rsa
SCRIPT

			  config.vm.provider "virtualbox" do |v|
				  v.customize [ "modifyvm", :id, "--cpus", "1" ]
				  v.customize [ "modifyvm", :id, "--memory", "1024" ]
				  v.customize [ "modifyvm", :id, "--cableconnected1", "on" ]
			  end

			  config.vm.network "private_network", ip: "192.168.200.72"
	  end
	  
	config.vm.define "centos8" do |config|
			  config.vm.hostname = "centos8.xyzinc.com"
			  config.vm.box = "bento/centos-8"
			  
			  config.vm.synced_folder "~/Downloads", "/home/vagrant/Downloads"

			  config.vm.provision "shell",
				  inline: <<SCRIPT
echo 'password!' | sudo passwd -f --stdin root
sudo ssh-keygen -t rsa -N ""  -f  /home/vagrant/.ssh/id_rsa
SCRIPT

			  config.vm.provider "virtualbox" do |v|
				  v.customize [ "modifyvm", :id, "--cpus", "1" ]
				  v.customize [ "modifyvm", :id, "--memory", "1024" ]
				  v.customize [ "modifyvm", :id, "--cableconnected1", "on" ]
			  end

			  config.vm.network "private_network", ip: "192.168.200.80"
	  end
	  
	config.vm.define "centos8-web" do |config|
			  config.vm.hostname = "centos8-web.xyzinc.com"
			  config.vm.box = "bento/centos-8"
			  
			  config.vm.synced_folder "~/Downloads", "/home/vagrant/Downloads"

			  config.vm.provision "shell",
				  inline: <<SCRIPT
echo 'password!' | sudo passwd -f --stdin root
sudo yum install -y httpd mariadb-server
sudo ssh-keygen -t rsa -N ""  -f  /home/vagrant/.ssh/id_rsa
SCRIPT

			  config.vm.provider "virtualbox" do |v|
				  v.customize [ "modifyvm", :id, "--cpus", "1" ]
				  v.customize [ "modifyvm", :id, "--memory", "1024" ]
				  v.customize [ "modifyvm", :id, "--cableconnected1", "on" ]
			  end

			  config.vm.network "private_network", ip: "192.168.200.81"
	  end
	  
	config.vm.define "centos8-ha" do |config|
			  config.vm.hostname = "centos8-ha.xyzinc.com"
			  config.vm.box = "bento/centos-8"
			  
			  config.vm.synced_folder "~/Downloads", "/home/vagrant/Downloads"

			  config.vm.provision "shell",
				  inline: <<SCRIPT
echo 'password!' | sudo passwd -f --stdin root
sudo yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
sudo yum install -y httpd mariadb-server varnish haproxy
sudo ssh-keygen -t rsa -N ""  -f  /home/vagrant/.ssh/id_rsa
SCRIPT

			  config.vm.provider "virtualbox" do |v|
				  v.customize [ "modifyvm", :id, "--cpus", "1" ]
				  v.customize [ "modifyvm", :id, "--memory", "1024" ]
				  v.customize [ "modifyvm", :id, "--cableconnected1", "on" ]
			  end

			  config.vm.network "private_network", ip: "192.168.200.82"
	  end
end