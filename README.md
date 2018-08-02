oVirt.engine-devel role
=========

The `oVirt.engine-devel` role configures a machine as an engine development environment -- check out code, install and configure postgresql,
configure repos, and install dependencies.

Requirements
------------

* Ansible version 2.5

Role Variables
--------------

| Name                     | Default value         | Description          |
|--------------------------|-----------------------|----------------------|
| username                 | UNDEF                 | user who will check out the code|
| project_dir              | UNDEF                 | directory into which the ovirt-engine code will be checked out (typically `/home/USER/git` or `/home/USER/projects`)|
| platform                 | UNDEF                 | platform (fc for Fedora or el for CentOS) to use for the yum repository |

Example Playbook
----------------

See more examples here https://github.com/gregsheremeta/ovirt-engine-devel-example

```yaml
---
- name: oVirt engine development environment
  hosts: localhost
  connection: local
  gather_facts: false
  become: true
  roles:
    - ovirt-engine-devel

  vars:
    platform: fc
    username: greg
    project_dir: /home/greg/git

```


License
-------

Apache License 2.0
