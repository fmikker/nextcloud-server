Role Name
=========

Ansible Playbook to install and configure NextCloud on a RHEL 7 / CentOS 7 machine.

Requirements
------------

This can be deployed on a bare CentOS 7 / RHEL 7 server, provided it has a working yum repository.

Description
------------

This role will: 

- Install EPEL and iuscommunity repos
- Install PHP56, MariaDB, httpd
- Configure MariaDB with default NextCloud DB, u/p nextcloud/nextcloud
- Create default login u/p admin/nextcloud

Role Variable Defaults (make changes in the file vars/main.yml)
--------------

DBName for MariaDB:   NextCloud
Username for MariaDB: nextcloud
Password for MariaDB: nextcloud

Dependencies
------------

There is no role dependency for this role.

Host File
----------

The host file for this role is hosts.target and the format is: 

[nextcloud]
IP FOR NEXTCLOUD SERVER

How to run the playbook
------------------------

**  Edit the variable file on vars/main.yml to set it to your environment. 

** Run the playbook

ansible-playbook -i hosts.target nextcloud-install.yml to install
ansible-playbook -i hosts.target nextcloud-remove.yml to cleanly remove

License
-------

GPLv3

Author Information
------------------

Kevin Holmes <kev@gokev.com> more at: https://github.com/GoKEV/
