wpgen
=========

This role is made only for testing things, do not use in production.
Using this role you will be able to install:

- mysql DB (2 databases included in provided variables)
- nginx web server with 2 listening domains
- 2 separate wordpress sites
- user with home dir where wordpress data will be stored

Requirements
------------

The Role tested on Debian 9.7 x64 (on standart Digital Ocean droplet), with ansible v.2.8.5.
Use this code with different OS or ansible version at your own risk!!!

Role Variables
--------------

domain_1: - will set your wordpress site dir name, nginx config name and server_name inside nginx config
domain_2: - will set your wordpress site dir name, nginx config name and server_name inside nginx config
user_name: - creates username with home dir where wordpress sites will be stored
wp_mysql_user - creates singe mysql DN user with GRANT permissions
wp_mysql_password - password for above mentioned mysql DB user
wp_mysql_db_1 - define mysql DB name to use with {domain_1} site
wp_mysql_db_2 - define mysql DB name to use with {domain_1} site

Dependencies
------------

There is no any dependencies you need to wary about

Example Playbook
----------------

---
- hosts: all
  remote_user: root
  become: yes
  vars:
    domain_1: 'wp-genesis-test1.com'
    domain_2: 'wp-genesis-test2.com'
    user_name: 'spanchbob'
    wp_mysql_user: 'spanchbob-db'
    wp_mysql_password: 'supersecretpass'
    wp_mysql_db_1: 'wp-genesis-test1_db1'
    wp_mysql_db_2: 'wp-genesis-test2_db2'
  roles:
    - wpgen


License
-------

BSD ( default ? )
You can use this without even asking someone, especialy me :)


Author Information
------------------

IT Switcher trying to be DevOps and to be hired in one of TOP 15 IT companies in my country.
So this is just a test task that i learned a lot from doing it.
