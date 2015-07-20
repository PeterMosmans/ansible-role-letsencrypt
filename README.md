Ansible Role: letsencrypt
=========

This role installs the latest git version of the Let's Encrypt Client: Getting and installing SSL/TLS certificates made easy. See for more information https://letsencrypt.readthedocs.org/en/latest/index.html


Requirements
------------

libssl-dev (or manually installed openssl development headers, libcrypto and libssl libraries)


Role Variables
--------------

Available variables are listed below, along with default values:

**letsencrypt_git**: The location where the git repository will be cloned to locally. The default location can be found in ```defaults/main.yml```.
```
letsencrypt_git: /var/git/letsencrypt
```



**letsencrypt_venv**: The location where the let's encrypt binaries will be stored (virtual Python environment). The default location can be found in ```defaults/main.yml```.
```
letsencrypt_venv: /usr/local/bin/letsencrypt 
```

Dependencies
------------

None.


Example Playbook
----------------

```
- hosts: all
  become: yes
  become_method: sudo
  roles:
    - role: PeterMosmans.letsencrypt
```
This example clones the letsencrypt client to the default location (```/var/git/letsencrypt```) and installs the virtual environment under ```/usr/local/bin/letsencrypt```. Afterwards, the binaries can be found under ```/usr/local/bin/letsencrypt/bin```.
The virtual environment can be activated using ```source /usr/local/bin/lensencrypt/bin/activate```, after which you can just use the ```letsencrypt``` command without preceding path. See for more information https://letsencrypt.readthedocs.org/en/latest/index.html




License
-------

GPLv3


Author Information
------------------

Created by Peter Mosmans.
