Security group
==============

A tiny role for convenient management of the security groups in Open Telekom Cloud.

Requirements
------------

It is required, that openstacksdk is installed on the execution host and connection to Open Telekom Cloud is provided.

Role Variables
--------------

    securitygroup_name: '' # creates security group with given name
    description: '' # creates a description of the security group
    rules:
      - protocol: '' # udp, gre, tcp, icmp
        port_range_min: '' # optional, 0 to 65535
        port_range_max: '' # optional, 0 to 65535
        remote_ip_prefix: '' # IP/netmask-suffix, 0.0.0.0/0 -> all IP adresses are allowed

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
