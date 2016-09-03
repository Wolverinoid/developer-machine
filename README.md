# developer-machine

Develop machine is a stuff for developers which helps to start develop web applications without installing 
environment to computer or laptop. 
This stuff creates virtual machine with all nesseccary components to start develop web application. 

It uses following components:
* [VirtualBox](https://www.virtualbox.org/) - a powerful x86 and AMD64/Intel64 virtualization product for enterprise as well as home use.
* [Vagrant](https://www.vagrantup.com/) - is computer software that creates and configures virtual development environments.
* [Ansible](https://www.ansible.com/) - is a free-software platform for configuring and managing computers which combines multi-node software deployment, ad hoc task execution, and configuration management.

The **developer-machine** contains **Vagrant** instructions to create virtual machine inside virtual box and configure this
virtual machine with **Ansible** instructions.

## Supported components

With developer-machine you can use following components:

* PHP
* NGINX
* PostgreSQL

Installation is based on **ubuntu/trusty64** virtualbox image.

## Installation

### On Linux

**VirtualBox**

```sh
$ sudo apt-get install virtualbox
```

For more information proceed to official site: https://www.virtualbox.org/

**Vagrant**


```
https://www.vagrantup.com/downloads.html
```


**Ansible**

```sh
$ sudo apt-add-repository ppa:ansible/ansible
$ sudo apt-get update
$ sudo apt-get install ansible
```

### On MacOS

**VirtualBox**

Download package from official site https://www.virtualbox.org/



**Vagrant**

Download package from official site https://www.vagrantup.com/downloads.html


**Ansible**

```sh
$ sudo easy_install pip
$ sudo pip install ansible
```

## Usage

To start using this tool it is necessary to make configuration. In provision folder there is an example file "example".

**Common settings**

In the **vagrantfile** specify folder where your projects will be placed:

```ruby
 config.vm.synced_folder "host_machine/path/", "virtual_machine/project", 
  :mount_options => ["dmode=777", "fmode=666"]
```

Here is setup for linux versions and main system folders:

```sh
os_distribution: ubuntu
os_distribution_release: trusty
os_usr_bin_dir: /usr/bin
os_usr_lib_dir: /usr/local/lib
```

You can find more config files inside of each ansible role inside **provision** folder. 

Rename example to all 

To build virtual machine just run:

```
vagrant up
```

To update configuration of virtual machine just run:

```
vagrant provision
```
