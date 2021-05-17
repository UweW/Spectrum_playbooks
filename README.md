# Spectrum Playbooks
ansible playbook for installing CA / Broadcom DX Netops Spectrum.

Requirements:
* ansible is available for any linux, but for the spectrum installation binaries it is necessary that you use a spectrum compatible linux for ansible
* tested with ansible 2.9 but versions > 2.5 should work
* clone the repository
* make sure name resolution is configured properly. Ansible host must be able to resolve the spectrum servers by name.


**how it works:**

* copy the Spectrum distribution file to the ansible machine
* create your inventory
The name use inventory.example as template and copy 
* run ansible


**tested combinations:**

|OS|Base Version|Update Version|
|----------|----------|----------|
|CentOS 8.1|10.4.3.0.21|10.4.3.1.17|
|Centos 8 Stream|10.4.3.0.21|10.4.3.1.17|



# fixes or enhancements


## Next todo's
- create roles
- create diffrent hostargs templates
- combine application role with templates

224
225
162
219