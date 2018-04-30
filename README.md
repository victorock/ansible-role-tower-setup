Ansible Tower Setup
=========

Simple Role to Setup Ansible Tower by Red Hat.

Requirements
------------

None

Role Variables
--------------

defaults/main.yml
```
ansible_tower_setup_version: "3.2.8"
ansible_tower_setup_dir: "/opt"
ansible_tower_setup_admin_password: "toweradmin"
ansible_tower_setup_pg_database: "tower"
ansible_tower_setup_pg_username: "tower"
ansible_tower_setup_pg_password: "tower"
ansible_tower_setup_rabbitmq_pass: "tower"

```

Dependencies
------------

The following dependencies are defined in `meta/main.yml`:

- role: geerlingguy.repo-epel
  when: ansible_os_family == 'RedHat'
- role: geerlingguy.ansible

Example Playbook
----------------

```YAML
- name: "Setup Ansible Tower by Red Hat"
  hosts: tower
  become: true

  roles:
    - victorock.ansible-tower-setup
```

License
-------

GPLv3

Author Information
------------------

Victor da Costa
