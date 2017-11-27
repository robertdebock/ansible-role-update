ansible-role-update
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-NAME.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-NAME)

Provides updates for your system.

Requirements
------------

Access to a repository containing packages, likely on the internet.

Role Variables
--------------

None known.

Dependencies
------------

- robertdebock.ansible-role-bootstrap

Download the dependencies by issuing this command:
```
ansible-galaxy install --role-file requirements.yml
```

Example Playbook
----------------

```
- hosts: servers

  roles:
    - ansible-role-update
```

Install this role using `galaxy install robertdebock.ansible-role-NAME`.


License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock <robert@meinit.nl>
