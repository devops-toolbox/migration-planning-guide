Role Name
=========

migration-planning-guide: Migration-planning-guide

[![Build Status](https://travis-ci.org/cmihai-ansible/migration-planning-guide.svg?branch=master)](https://travis-ci.org/cmihai-ansible/migration-planning-guide)

Ansible galaxy:
---------------

[https://galaxy.ansible.com/devops-toolbox.migration-planning-guide](https://galaxy.ansible.com/devops-toolbox.migration-planning-guide)

```bash
ansible-galaxy install devops-toolbox.migration-planning-guide
```

Requirements
------------

- For RHEL, a Red Hat subscription or functional local repository.
- Ansible 2.4 or higher

Role Variables
--------------

```yaml
migration-planning-guide_packages_state: present
migration-planning-guide_remove_packages: true
migration-planning-guide_enable_service: true
migration-planning-guide_enable_selinux: true
migration-planning-guide_copy_templates: true
migration-planning-guide_firewall_configure: true
migration-planning-guide_firewall_rules:
  - service: ssh
  - port: 3389
migration-planning-guide_users:
  - user: devops
    group: docker
migration-planning-guide_selinux_booleans:
  - name: ftp_home_dir
    state: true
    persistent: true
```

Dependencies
------------

- For Red Hat, subscription-manager.

Example Playbook
----------------

```yaml
---
- name: Install migration-planning-guide on localhost
  hosts:
    - localhost
  connection: local

  tasks:
    - name: migration-planning-guide is configured
      import_role:
        name: devops-toolbox.migration-planning-guide
      vars:
        migration-planning-guide_packages_state: present
        migration-planning-guide_remove_packages: true
        migration-planning-guide_enable_service: true
        migration-planning-guide_enable_selinux: true
        migration-planning-guide_copy_templates: true
        migration-planning-guide_firewall_configure: true
        migration-planning-guide_firewall_rules:
          - service: ssh
          - port: 3389
        migration-planning-guide_users:
          - user: devops
            group: docker
        migration-planning-guide_selinux_booleans:
          - name: ftp_home_dir
            state: true
            persistent: true
      tags: migration-planning-guide
```

License
-------

MIT

Author Information
------------------

- [Mihai Criveti](https://www.linkedin.com/in/devops-toolbox.)
