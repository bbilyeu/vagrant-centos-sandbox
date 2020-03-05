# Overview 
This is a stupidly simple and lazy path to setup CentOS 7.7 and CentOS 8 VMs for training, practice, etc.

> **NOTE #1**: This setup assumes a CentOS 7.7 host OS. 
> **NOTE #2**: This assumes any/all `vagrant` commands are run from "$HOME/vagrant-centos-sandbox".
 
## Pre-requisites 
1. CentOS 7 device (laptop/desktop/server)
2. A clone of this repo
3. Internet access

### 1. Clone this repo
```
cd $HOME
git clone https://github.com/bbilyeu/vagrant-centos-sandbox.git
```

### 1. Install necessary components
```
## [root] Install kernel-headers, gcc, perl, and make
yum install gcc make perl kernel-devel
## [root] Install Virtualbox 6.1.2
yum install https://download.virtualbox.org/virtualbox/6.1.2/VirtualBox-6.1-6.1.2_135662_el7-1.x86_64.rpm
## [root] install Vagrant
yum install https://releases.hashicorp.com/vagrant/2.2.7/vagrant_2.2.7_x86_64.rpm
```

#### 2. Add Vagrant 'Box' providers, install VirtualBox Guest Plugin
```
## [user] import VM providers
vagrant box add bento/centos-7.7 --provider virtualbox
vagrant box add bento/centos-8 --provider virtualbox
## [user] Install the VirtualBox guest plugin
vagrant plugin install vagrant-vbguest
```

#### 3. Start up desired VM(s)
```
cd "$HOME/vagrant-centos-sandbox"
vagrant up $vmName
```
For reference: 
| vmName | OS Version | Additional Packages |
| ------ | ---------- | -------- |
| centos7 | CentOS 7.7 | n/a |
| centos7-web | CentOS 7.7 | httpd, mariadb-server |
| centos7-ha | CentOS 7.7 | httpd, mariadb-server, epel repo, varnish, haproxy |
| centos8 | CentOS 8.0 | n/a |
| centos8-web | CentOS 8.0 | httpd, mariadb-server |
| centos8-ha | CentOS 8.0 | httpd, mariadb-server, epel repo, varnish, haproxy |

#### 4. Enter VM and you're done
```
vagrant ssh $vmName
	# base un/pw: vagrant // vagrant
	# root un/pw: root // password!
```

### Final notes
Final cheat-sheet commands for Vagrant:
```
## delete VM
vagrant destroy $vmName

## rebuild VM
vagrant destroy -f $vmName; vagrant up $vmName

## stop VM (non-destructive)
vagrant half $vmName

## see all VMs
vagrant global-status
```