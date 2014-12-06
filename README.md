Role Name
=========

Ansible role to setup common Oracle stuff.

- Setup Oracle groups (oinstall, oper, dba, asmdba, asmoper, ...)
- Setup Oracle users (oracle, grid)

Requirements
------------

No requirements yet.

Role Variables
--------------

oracle_app_directory: /u01/app
oracle_inventory_group_name: oinstall
oracle_inventory_group_id: 54321
oracle_inventory_directory: '{{ oracle_app_directory }}/oraInventory'
oracle_inventory_file: '{{ oracle_inventory_directory }}/ContentsXML/inventory.xml'

oracle_db_osdba_group_name: dba
oracle_db_osdba_group_id: 54322
oracle_db_osoper_group_name: oper
oracle_db_osoper_group_id: 54323
oracle_db_osbackupdba_group_name: backupdba
oracle_db_osbackupdba_group_id: 54324
oracle_db_osdgdba_group_name: dgdba
oracle_db_osdgdba_group_id: 54325
oracle_db_oskmdba_group_name: kmdba
oracle_db_oskmdba_group_id: 54326

oracle_db_owner_user_name: oracle
oracle_db_owner_user_id: 54321
oracle_db_owner_user_home: /home/oracle
oracle_db_owner_user_shell: /bin/bash
oracle_db_oracle_base: "{{oracle_app_directory}}/{{ oracle_db_owner_user_name }}"

oracle_gi_osdba_group_name: asmdba
oracle_gi_osdba_group_id: 54327
oracle_gi_osoper_group_name: asmoper
oracle_gi_osoper_group_id: 54328
oracle_gi_osasm_group_name: asmadmin
oracle_gi_osasm_group_id: 54329

oracle_gi_owner_user_name: grid
oracle_gi_owner_user_id: 54322
oracle_gi_owner_user_home: /home/grid
oracle_gi_owner_user_shell: /bin/bash
oracle_gi_oracle_base: "{{ oracle_app_directory }}/{{ oracle_gi_owner_user_name }}"

oracle_shells:
- path: /bin/bash
  file: .bash_profile
- path: /bin/sh
  file: .profile
- path: /bin/ksh
  file: .profile
- path: /bin/csh
  file: .login
- path: /bin/tcsh
  file: .login

Dependencies
------------

No dependencies.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: Nosmoht.ansible-role-oracle-common }

License
-------

BSD

Author Information
------------------

Name: Thomas Krahn
mail: ntbc@gmx.net

