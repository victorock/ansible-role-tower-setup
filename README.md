Ansible Tower Setup
=========

Simple Role to Setup Ansible Tower by Red Hat.

Requirements
------------

Repository containing:
  - ansible
  - @Development Tools

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

None

Example Playbook
----------------

```YAML
- name: "Setup Ansible Tower by Red Hat"
  hosts: tower
  become: true

  roles:
    - victorock.tower_setup
```

```YAML
- name: "Setup Ansible Tower by Red Hat (custom)"
  hosts: tower
  become: true

  roles:
    - role: victorock.tower_setup
      tower_setup_version: "3.3.0-1"
      tower_setup_admin_password: "mypassword"
      tower_setup_pg_password: "mydbpassword"
```

```YAML
- name: "Setup (locally) Ansible Tower by Red Hat (custom)"
  hosts: localhost
  connection: local
  become: true

  roles:
    - role: victorock.tower_setup
      tower_setup_version: "3.3.0-1"
      tower_setup_admin_password: "mypassword"
      tower_setup_pg_password: "mydbpassword"
```


License
-------

GPLv3

Author Information
------------------

Victor da Costa
