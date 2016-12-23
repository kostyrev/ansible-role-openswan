openswan
=========

[![Build Status](https://travis-ci.org/kostyrevaa/ansible-role-openswan.svg?branch=master)](https://travis-ci.org/kostyrevaa/ansible-role-openswan)

This role installs and configures [openswan](https://www.openswan.org)

Requirements
------------

None

Role Variables
--------------

| Name                                | Description                                |
|-------------------------------------|--------------------------------------------|
| openswan_config_options             | Hash config setup                          |
| openswan_manage_service             | Notify ipsec service when templates change |

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: all
  vars:
    openswan_connections:
      mdpu:
        gateway_public_ip: 55.231.144.167
        psk: '123321'
        options:
          - left: "{{ ansible_default_ipv4.address }}"
          - leftsubnets: '10.45.0.0/16'
          - leftnexthop: '%defaultroute'
          - right: 'tncvpn.massdpu.com'
          - rightsubnets: 10.199.131.0/24
          - pfs: 'no'
          - forceencaps: 'yes'
          - authby: 'secret'
          - auto: 'start'
  roles:
    - role: kostyrevaa.openswan
```


License
-------

BSD

Author Information
------------------

Aleksandr Kostyrev
