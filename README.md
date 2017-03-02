# Ansible Role: SSH
[![Build Status](https://travis-ci.org/Furdarius/ansible-ssh.svg?branch=master)](https://travis-ci.org/Furdarius/ansible-ssh)

Automated security-target SSH configuration.

## Install

```bash
ansible-galaxy install Furdarius.SSH
```

## Variables

All variables can be found in [defaults/main.yml](https://github.com/Furdarius/ansible-ssh/blob/master/defaults/main.yml)

## Playbook example

```yaml
---
- hosts: all
  become: true
  roles:
    - ssh
  vars:
    ssh_port: 12013
    users:
      - { name: admin, sudoers: false, password: "76523494", public_key: ./keys/admin_key.pub }
      - { name: ansible, sudoers: true, public_key: ~/.ssh/id_rsa.pub }
```
