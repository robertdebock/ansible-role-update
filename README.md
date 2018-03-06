update
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-update.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-update)

Provides updates for your system.

Requirements
------------

Access to a repository containing packages, likely on the internet.

Role Variables
--------------

- update_autoremove: Clean unused packages? (For APT distributions only)
- update_upgrade_command: Type of upgrade: dist, yes, safe, or full.  (For APT distributions only)
- update_cache_valid_time: Update the cache if it's older than the cache valid time (For APT distributions only)
- update_reboot: Control the desired reboot behaviour. Set to "yes" (default) or "no".

Dependencies
------------

This role can be used to prepare your system:

- robertdebock.bootstrap

Download the dependencies by issuing this command:
```
ansible-galaxy install --role-file requirements.yml
```

Example Playbook
----------------

The simplest way possible:
```
- hosts: servers

  roles:
    - robertdebock.bootstrap
    - robertdebock.update
```

The role sets a variable so it's possible to understand if changes were made:
- update_result

Here is an example of how to use that variable:
```
- hosts: servers

  roles:
    - robertdebock.update

  tasks:
    - name: send email
      mail:
        to: sysadmin@example.com
        subject: "server {{ ansible_hostsname }} updated"
      when:
        - update_result.changed
```

Install this role using `galaxy install robertdebock.update`.

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock <robert@meinit.nl>
