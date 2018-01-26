update
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-update.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-update)

Provides updates for your system.

Requirements
------------

Access to a repository containing packages, likely on the internet.

Role Variables
--------------

None known.

Dependencies
------------

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
    - robertdebock.update
```

The role sets a variable so it's possible to understand if changes were made:
- ansibleroleupdate

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
        - ansibleroleupdate.changed
```

Install this role using `galaxy install robertdebock.update`.

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock <robert@meinit.nl>
