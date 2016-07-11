Short Description
-----------------
A `unofficial fork` from [the official openstack ansible playbooks] (github.com/openstack/openstack-ansible) to install Openstack components (The original using `git` and github to build Openstack from source code). 

All packages will be installed from appropriate repository except `python-openstackclient` because of ([this bug](https://bugs.launchpad.net/python-openstackclient/+bug/1560157) ignoring `.

I have also faced the same problem with `python-neutronclient` ([detailed bug] (https://bugs.launchpad.net/python-neutronclient/+bug/1538959)) but I failed to resolve using pip install with `--upgrade` options. At the end of that link I saw problem was fixed and merged to the master, I hope this fix will be available in pip soon. Till that time, we have to patch code manually from the code in the link below.

How to use the playbook
-----------------------

#### The simplest way: 
`ansible-playbook -i inventory.ini -e @user_secret.yml setup-everything.yml`

#### The hard way:

- **Preparing environment:** `ansible-playbook -i inventory.ini -e @user_secret.yml setup-infra.yml`
- **Database Server:** `ansible-playbook -i inventory.ini -e @user_secret.yml os-database.yml`
- **Identity Service:** `ansible-playbook -i inventory.ini -e @user_secret.yml os-keystone-setup.yml`
- **Image Service:** `ansible-playbook -i inventory.ini -e @user_secret.yml os-glance-setup.yml`
- **Compute Service:** `ansible-playbook -i inventory.ini -e @user_secret.yml os-nova-setup.yml`
- **Network Service:** `ansible-playbook -i inventory.ini -e @user_secret.yml os-neutron-setup.yaml`
- **Block Storage Service:** `ansible-playbook -i inventory.ini -e @user_secret.yml os-cinder-setup.yml`
- **Dashboard:**  `ansible-playbook -i inventory.ini -e @user_secret.yml os-dashboard-setup.yml`

TO DO
------

* Update Deployment Topologies

11/07/2016
----------

* `lvm` is the only backend for cinder supported at this time
* Supported network scenario: `provider`
* Supported provider network type: `vlan, flat`
* Supported tentnat network: `None`
* Supported mechanism: `linuxbridge`
* `Non HA` (single controller) architecture
* Supported OS: `Ubuntu 14.04`

Under Development
-----------------

This is not the fist time I write a playbook to install Openstack environment but is one that I work in a 'proper procedures', so I will update as soon as I fixed issues and implemented a new things. Any comments please reach me at d0m0reg00dthing@gmail.com.
