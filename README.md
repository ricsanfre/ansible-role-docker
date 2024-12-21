Ansible Docker Role
=========

[![CI](https://github.com/ricsanfre/ansible-role-docker/actions/workflows/ci.yml/badge.svg)](https://github.com/ricsanfre/ansible-role-docker/actions/workflows/ci.yml)

Install and configure Docker on Linux.

Requirements
------------

None


Role Variables
--------------

Available variables are listed below along with default values (see `defaults\main.yaml`)


    docker_users: []

A list of system users to be added to the docker group (so they can use Docker on the server without root priveges).

```yml
docker_users:
  - user1
  - user2
```
   docker_daemon_options: {}

Custom dockerd options can be configured through this dictionary representing the json file /etc/docker/daemon.json.

```yml
docker_daemon_options:
  exec-options: "["native.cgroupdriver=systemd"]"
  storage-driver: "overlay"
  log-driver: "json-file"
  log-opts:
    max-size: "100m"
  data-root: "/data/docker"
```

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