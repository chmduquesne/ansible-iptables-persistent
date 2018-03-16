Role Name
=========

chmduquesne.ansible-iptables-persistent

Requirements
------------

Debian

Role Variables
--------------

No role variables.

This role is meant to be used with the official iptables module. The idea
is to use the handler "persist iptables" whenever adding any iptable rule
from within a role.

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - chmduquesne.ansible-iptables-persistent

License
-------

BSD
