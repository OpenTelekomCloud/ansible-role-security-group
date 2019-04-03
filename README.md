Security group
==============

A tiny role for convenient management of the security groups in openstack

Requirements
------------

It is required, that openstacksdk is installed on the execution host and connection to the OTC is provided.

Role Variables
--------------

A description of the setable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

-

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      vars:
        rules:
          - protocol: tcp
            port_range_min: 80
            port_range_max: 80
            remote_ip_prefix: 0.0.0.0/0
          - protocol: icmp
            remote_ip_prefix: 0.0.0.0/0
          - protocol: udp
            remote_ip_prefix: 0.0.0.0/0
      roles:
        - { role: opentelekomcloud.security_group, securitygroup_name: 'my_test', description: 'some descr' }
  
Example for deleting a security group.
    
    - hosts: localhost
      roles:
        - { role: opentelekomcloud.security_group, state: 'absent', securitygroup_name: 'my_test' }

License
-------

BSD

Author Information
------------------

Open Telekom Cloud
