Role's roles
------------

Setting a cluster stack with corosync (Cluster's Communication System) & pacemaker (Cluster Resource Manager) to support Openstack High Availability deployment

This role going to do the following:
* Installing and configuring corosync
	* 3 Nodes scenario
	* Transport: UDP Unicast
	* Single Ring: Ring-0
	* Using `ansible_default_ipv4` as default comminication address
	* Disable mutual authentication (To simplify the installation)

* Installing and configuring pacemaker
	* Pre-configure some options:
		  - pe-warn-series-max: 100
		  - pe-input-series-max: 1000
		  - pe-error-series-max: 1000
		  - cluster-recheck-interval: "5min"
		  - stonith-enabled: "false"
		  - no-quorum-policy: "ignore"
	* Adding resources:
		- VIP Resource for 3 controller node