Role's roles
============

Setting up a keystone (Identity) environment to provide authentication/authorization service to all other Openstack services. 

This role will do the following:
* Create database for keystone and ensure priviledges to `keystone` user
* Install & configure Apache Webserver (SSL enabled if needed) to service user/service requestes.
* Create and install self-sigined SSL certificate as well as user-provide SSL certificate.
* Install `python-openstackclient` from pip instead of one from official repository to fix some issues with `neutronclient` if you are going to use SSL for `neutron-server`
* Create client credential and place it into the first controller node (at /root/admin-openrc) (base on inventory config)
* Create and/or rotate fernet key
* Create configured domain(s)/region(s)/user(s)/service(s)/endpoint(s)/role(s) and the mapping user(s) <=> role(s)

Requirements
------------

* A running database server (MySQL/MariaDB): to create `keystone` database