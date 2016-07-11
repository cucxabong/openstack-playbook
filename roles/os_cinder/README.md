Role's roles
------------

Setting up and configuring cinder (Openstack Block Storage) to provide block device to instances.

This role is going to do the following:
* Create database for cinder and ensure priviledges to `cinder` user
* Create configured service/user/endpoint and the mapping user(s) <=> role(s)
* Create and install self-sigined SSL certificate as well as user-provide SSL certificate.
* Supported backends: lvm
* Using Apache Webserver to provide SSL security for cinder-api (native openstack did not support SSL :( ))
* Using `tgt` as iSCSI helper

Requirements
------------

* A running database (MySQL/MariaDB) SQL server
* A running keystone (identity service) for user/role mapping/service/endpoint creating.

