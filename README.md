# Spectrum Playbooks
ansible playbook to install CA/Broadcom DX Netops Spectrum.

**Requirements:**
* ansible is available for any linux, but for the Spectrum installation binaries it is necessary that you use a Spectrum compatible linux for ansible
* tested with ansible 2.9 but versions => 2.5 should work
* clone of this repository
* properly configured name resolution. Ansible host must be able to resolve the Spectrum servers by name.
* licensed Spectrum distributed installation archives
* allowed communication from ansible host port 22/tcp and 46517/tcp to Spectrum servers


**how it works:**

* copy the Spectrum distribution file to the ansible machine and unpack the archive
* create your inventory 
  * use inventory.example as template and name it for example inventory.mySpectrum
  * follow the comments in the template and modify your inventory file
* run ansible 'ansible-playbook install-spectrum.yml -i inventory.mySpectrum'

**tested combinations:**

|Ansible/Installation Host|Server OS|Base Version|Update Version|
|----------|----------|----------|----------|
|CentOS 7.9|CentOS 8.1|10.4.3.0.21|10.4.3.1.17|
|CentOS 7.9|Centos 8 Stream|10.4.3.0.21|10.4.3.1.17|



### fixes or enhancements


### Next todo's
- create roles
- create diffrent hostargs templates
- combine application role with templates

224
225
162
219