# Ansible-roles

[![Build Status](https://travis-ci.org/sgmac/ansible-roles.svg?branch=master)](https://travis-ci.org/sgmac/ansible-roles)

This is just a repository holding all the ansible repositories I already have added to my github account. The idea is to clone this repository
when using something like `cloud-init`.

**ansible.cfg**

Do not forget to update the `roles_path` accordingly.

```
[defaults]
roles_path = ~/ansible-roles
host_key_checking=False
```


## Roles

Please, read the default variables and set according to your needs.

- [golang](golang.md)
- [ansible-ssh](ansible-ssh.md)
- [ansible-user](ansible-user.md)
