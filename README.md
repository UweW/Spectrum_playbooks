# Spectrum Playbooks
ansible playbook to install CA/Broadcom DX Netops Spectrum.
The playbook help you set up any size of spectrum environments.
It uses the Spectrum distributed installation procedure and all the Spectrum servers will be installed in parallel.
The minor version will be installed and also the latest update if defined.
You only need one configuration file (inventory) to define your environment!

You can define server with these functions:
* SpectroSERVER primary and secondary
* OneClick
* Spectrum Report Manager

or any valid combination.

To give you an idea of the installation time I measured in my lab:
* 2 SpectroSERVER (1 primary and 1 secondary with Oneclick) : 28 min
* 4 SpectroSERVER (2 primary and 2 secondary, one with SRM and Oneclick): 31 min

**Requirements:**
* fresh Linux server/VMs for Spectrum
* a user with sudo rights to run the installation
* ansible is available for any linux derivate, but for the Spectrum installation binaries it is necessary that you use a Spectrum compatible linux for ansible
* tested with ansible 2.9 but versions => 2.5 should work
* clone of this repository
* properly configured name resolution. Ansible host must be able to resolve the Spectrum servers by name.
* licensed Spectrum distributed installation archives
* allowed communication from ansible host to Spectrum servers port 22/tcp and 46517/tcp

**how it works:**

* copy the Spectrum distribution file to the ansible machine and unpack the archive
* create your inventory 
  * use inventory.example as template and name it for example inventory.mySpectrum
  * follow the comments in the template and customize your inventory file
* run ansible 'ansible-playbook install-spectrum.yml -i inventory.mySpectrum'

**what does the playbook do for you:**

* Installs all missing required rpm packages
* set SELINUX to permissive
* disable firewalld
* create user for Spectrum
* give spectrum user the necessary sudoers rights
* install sradmin
* prepare hostargs and password files from inventory 
* add all spectrum server in /etc/hosts
* install Spectrum minor version
* load ssdb with presedence 20 on secondarys
* add all spectrum server to hostrc
* install Spectrum update 
* start Spectroserver


**tested combinations:**

|Ansible/Installation Host|Server OS|Base Version|Update Version|
|----------|----------|----------|----------|
|CentOS 7.9|CentOS 8.1|10.4.3.0.21|10.4.3.1.17|
|CentOS 7.9|Centos 8 Stream|10.4.3.0.21|10.4.3.1.17|

#### Next todo's
- migrate to ansible roles

[x] add xorg-x11-server-Xvfb and start option for webapp

[ ] $SPECROOT>webtomcat>bin directory and execute the following command:./startWebTomcat.sh 
