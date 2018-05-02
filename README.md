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

```YAML
dependencies:
  - role: geerlingguy.repo-epel
    when: ansible_os_family == 'RedHat'
  - role: geerlingguy.ansible
  - role: geerlingguy.pip
    pip_install_packages:
      - name: ansible-tower-cli
        virtualenv: "/var/lib/awx/venv/awx"
      - name: ansible-tower-cli
        virtualenv: "/var/lib/awx/venv/ansible"
      - name: ncclient
        virtualenv: "/var/lib/awx/venv/awx"
      - name: ncclient
        virtualenv: "/var/lib/awx/venv/ansible"
      - name: f5-sdk
        virtualenv: "/var/lib/awx/venv/awx"
      - name: f5-sdk
        virtualenv: "/var/lib/awx/venv/ansible"
      - name: f5-icontrol-rest
        virtualenv: "/var/lib/awx/venv/awx"
      - name: f5-icontrol-rest
        virtualenv: "/var/lib/awx/venv/ansible"
      - name: ipaddress
        virtualenv: "/var/lib/awx/venv/awx"
      - name: ipaddress
        virtualenv: "/var/lib/awx/venv/ansible"
      - name: passlib
        virtualenv: "/var/lib/awx/venv/awx"
      - name: passlib
        virtualenv: "/var/lib/awx/venv/ansible"
      - name: pandevice
        virtualenv: "/var/lib/awx/venv/awx"
      - name: pandevice
        virtualenv: "/var/lib/awx/venv/ansible"
      - name: pan-python
        virtualenv: "/var/lib/awx/venv/awx"
      - name: pan-python
        virtualenv: "/var/lib/awx/venv/ansible"

```

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
