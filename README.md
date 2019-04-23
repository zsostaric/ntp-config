Ansible role for NTP configuration
=========

This role will configure NTP to use prefered NTP servers.

Description
------------

This role will first stop and disable cronyd (if present) and set 2 common NTP servers:

0.europe.pool.ntp.org
1.europe.pool.ntp.org

It will also set a prefered NTP server on the first server:

hr.pool.ntp.org

And another prefered NTP server on the second server:

si.pool.ntp.org

Requirements
------------

For this to work (prefered server) it is mandatory to set the variable ntp_server_prefered in the inventory list per server. For example:

[servers]
192.168.6.10    ntp_server_prefered=hr.pool.ntp.org
192.168.6.11    ntp_server_prefered=si.pool.ntp.org

Supported Systems
------------

Tested on CentOS 7.0.1406 and CentOS 7.6.1810.

Variables
--------------

Variables for ntp.conf can be changed in defaults/main.yml.
Global variables can be changed in vars/main.yml

Example Playbook
----------------

    - hosts: servers
      roles:
         - ntp-config


