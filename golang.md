Ansible Go Role
===============

The role installs Go pinned to a specific version, optionally setups the environment  for an user.

 * downloads a versioned tarball 
 * installs go in the default path ```/usr/local/go```
 * user envrionment

Variables
---------
Here is a list of all the default variables for this role.

```yaml
user: ""
version: "1.6.1"
tarfile: "go{{version}}.linux-amd64.tar.gz"
gocode: "gocode"
gopath: "/home/{{user}}/{{gocode}}"
sh: "bash"
```

Example Playbook
----------------

The role works with different Go versions by using symlinks. If you have already installed  version ```1.4.1``` and you want to test
something for Go ```1.3.1``` you can do it. 

You will find a new symlink ```/usr/local/go  -> /usr/local/go{{version}}```. This is done this way only for testing purpose.

1.) **Install a version of Go**

```yaml
    - hosts: servers
      roles:
         - { role: golang, version: "1.4.1"}
```
2.) **Configure environment for an user**

```yaml
    - hosts: servers
      roles:
         - { role: golang, user: "deploy", version: "1.4.1"}
```

You may change the $GOPATH as well. Currently only supporting ```linux amd64```.
