Role Name
=========

chmduquesne.ansible-iptables-persistent

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
         - chmduquesne.ansible-iptables-persistent
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
