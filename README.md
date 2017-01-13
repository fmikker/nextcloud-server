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

Caveats for manual setup steps:
- To maintain the integrity of NextCloud, no modifications were done to the install php file.  It will still need to install in its own way, using its own salted hash methods.  As a result of this, you'll need to manually change the DB type to MariaDB and enter the credentials in from below.  These default values are set in main/vars.yml and can be changed to whatever SQL values you wish.  By default, they are:


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
