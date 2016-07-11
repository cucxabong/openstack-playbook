Role's role
-----------

Setting up `glance` (Image Service) to provide template to Openstack Compute and Openstack Cinder.

This role do the following:
* Create SQL Database and ensure priviledges to `glance` user
* Create configured Glance service/endpoint/user and the mapping user(s) <=> role(s)
* Create and install self-sigined SSL certificate as well as user-provide SSL certificate.
* Support backends: file

Requirements
------------

* A running database (MySQL/MariaDB) SQL server
* A running keystone (identity service) for user/role mapping/service/endpoint creating.