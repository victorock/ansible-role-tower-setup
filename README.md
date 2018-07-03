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
tower_setup_version: "3.2.5"
tower_setup_dir: "/opt"
tower_setup_admin_password: "toweradmin"
tower_setup_pg_database: "tower"
tower_setup_pg_username: "tower"
tower_setup_pg_password: "tower"
tower_setup_rabbitmq_pass: "tower"

```

Dependencies
------------

The following dependencies are defined in `meta/main.yml`:

```YAML
dependencies:
  - role: geerlingguy.repo-epel
    when: ansible_os_family == 'RedHat'
  - role: geerlingguy.ansible

```

Example Playbook
----------------

```YAML
- name: "Setup Ansible Tower by Red Hat"
  hosts: tower
  become: true

  roles:
    - victorock.tower_setup
```

License
-------

GPLv3

Author Information
------------------

Victor da Costa
