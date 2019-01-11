[![Build Status](https://travis-ci.org/chmduquesne/ansible-iptables-persistent.svg?branch=master)](https://travis-ci.org/chmduquesne/ansible-iptables-persistent)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-chmduquesne.iptables_persistent-blue.svg)](https://galaxy.ansible.com/chmduquesne/iptables_persistent/)

Role Name
=========

chmduquesne.iptables-persistent

Requirements
------------

Ansible 2.2+ on a Debian-based system

Role Variables
--------------

None

Dependencies
------------

None

Example Playbook
----------------

The idea of this role is to set iptables rules from the relevant role
(e.g. with ansible's native module), and to call the handler
`persist iptables` when doing so. This will save ipv4 and ipv6 rules.

    - hosts: servers
      roles:
        - chmduquesne.iptables_persistent
      tasks:
        - name: "add some iptable rule"
          iptables:
            chain: INPUT
            source: 8.8.8.8
            jump: DROP
          become: yes
          notify:
            - persist iptables

License
-------

BSD
