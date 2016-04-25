Ansible SSH Role
===============
[![Build Status](https://travis-ci.org/sgmac/ansible-ssh.svg?branch=master)](https://travis-ci.org/sgmac/ansible-ssh)

The role installs and configures a OpenSSH server. 

Variables
---------
Here is a list of all the default variables for this role.

```yaml
---
allow_users: deploy
deny_users: root
port: 22
permit_root_login: 'no'
pub_key_authentication: 'yes'
password_authentication: 'no'
use_pam: 'yes'
enable_ftp: 'yes'
```

Example Playbook
----------------

It's important to use single quotes when using 'yes' or 'not'. Withouth single quoutes is evaluted to **False** or **True** and that value is placed in the template. As a result the server does not start.

As you may already seen,  __password_authentication__ is disabled by default. If you do not specify **allow_users** that have their proper public key deployed, you will get locked up.

1.) **Install SSH**

```yaml
    - hosts: servers
      roles:
         - ansible-ssh
```
2.) **Allow users**

```yaml
    - hosts: servers
      roles:
         - { role: ansible-ssh, allow_users: deploy git}
```

2.) **Deny users**

```yaml
    - hosts: servers
      roles:
         - { role: ansible-ssh, deny_users: root, enable_ftp: 'yes'}
```

