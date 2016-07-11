Role's roles
------------

Setting up and configuring `neutron` (Openstack Network Service) which provide ingress/egress network connectivity to/from instances.

This role is going to do the following:

* Create SQL Database and ensure priviledges to `glance` user
* Create configured Glance service/endpoint/user and the mapping user(s) <=> role(s)
* Create and install self-sigined SSL certificate as well as user-provide SSL certificate.
* Supported network scenario: provider & self-service network
* Supported provider network types: flat, vlan
* Supported tenant network types: vlan, vxlan, gre
* Supported neutron plugins: linuxbridge, openvswitch

Requirements
------------

* A running database (MySQL/MariaDB) SQL server
* A running keystone (identity service) for user/role mapping/service/endpoint creating.