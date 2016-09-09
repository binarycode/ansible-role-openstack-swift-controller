Ansible Role: OpenStack Swift Controller Node
=============================================

This role installs and configures OpenStack Swift Controller Node on EL7 system.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`)

    openstack_admin_password: admin

`admin` OpenStack user password.

    openstack_region: RegionOne

OpenStack region.

    swift_password: swift

Swift password.

    swift_partition_power: 10
    swift_replicas: 3

Create Swift ring with `2^swift_parition_power` partitions and `swift_replicas` replicas.

    nodes: []

Array of swift nodes to configure (each item should look like `{ zone: 1, ip: '10.0.0.101', device: 'sdb' }`).

    swift_suffix: swift
    swift_prefix: swift

Prefix and suffix to be used by swift.

Dependencies
------------

* `binarycode.crudini`

Example Playbook
----------------

    - hosts: servers
      roles:
         - binarycode.openstack-swift-controller

License
-------

BSD

Author Information
------------------

[Igor Sidorov](https://github.com/binarycode)
