Role's roles
------------

Settingn up and configuring nova (Openstack Compute Service) to provide instance compute resources.

This role going to do the following:
* Create database for nova and ensure priviledges to `nova` user
* Create configured service/user/endpoint and the mapping user(s) <=> role(s)
* Create and install self-sigined SSL certificate as well as user-provide SSL certificate.

Requirements
------------

* A running database (MySQL/MariaDB) SQL server
* A running keystone (identity service) for user/role mapping/service/endpoint creating.