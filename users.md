Ansible User
===============

The role defines an user and its primary group.

Variables
---------
Here is a list of all the default variables for this role.

```yaml
---
user: "deploy"
group: "admin"
bash: "/bin/bash"
hashed_password: ""
pub_key: ""
```

Example Playbook
----------------
Bear in mind you need to provide at least `hashed_password`.
You can generate a password using mkpasswd, it's not good a idea to keep hashed passwords in git repositories, take this as an illustrated example.
```
# mkpasswd --method=SHA-512
Password: (Ansible)
$1$QobYRhO1$biTZsqxniYM/ZgLD1TBC80
```

1.) **Add user**

```yaml
    - hosts: servers
      roles:
	  - {role: users , hashed_password: <HASHED_PASSWORD_HERE> }
```
2.) **Provide public key**

The `pub_key` path is relative to where your play is located.

```yaml
    - hosts: servers
      roles:
         - { role: users, hashed_password: <HASHED_PASSWORD_HERE>,  pub_key: keys/my_pub_key.pub}
```
