Ansible Docker Role
=========

Install and configure Docker on Linux.

Requirements
------------

None


Role Variables
--------------

Available variables are listed below along with default values (see `defaults\main.yaml`)


    docker_group_users: []

Linux users to be created/present and added to docker group. Enabling non-root docker execution

   docker_storage_driver: overlay2
   docker_data_dir: /var/lib/docker

Docker daemon (daemon.json) configuration

Dependencies
------------

None

Example Playbook
----------------



```
---
- hosts: docker
  vars:
    ansible_user: ansible
    ansible_become: yes
    
  roles:
    - docker
```

License
-------

MIT/BSD

Author Information
------------------

Ricardo Sanchez (ricsanfre)