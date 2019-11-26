Role Name
=========

[![Build Status](https://travis-ci.com/frite/ansible-role-recon-package-manager.svg?branch=master)](https://travis-ci.com/frite/ansible-role-recon-package-manager)

A role to handle package operations (i.e. prerequisites for tools etc.) for Recon.

Requirements
------------

Basically none.

Role Variables
--------------
Depending on the OS, you are going to need to set different variables.

For `apt` (i.e. Debian, Ubuntu, Debian-based), you need something like the following:
```
apt_packages:
  - nmap
```

For `yum` (i.e. CentOS 7), you need something like the following:
```
yum_packages:
  - nmap
```

For `dnf` (i.e. CentOS 8), you need something like the following:
```
dnf_packages:
  - nmap
```

It won't autoupdate by default or autoremove packages by default.
If you want this functionality, you need to 
```
pkg_mgr_updates: true # for updates
pkg_mgr_autoremoves: true # to autoremove unneeded packages
```
Example Playbook
----------------

Including an example of how to use your role (for instance, with variables
passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: ansible-role-recon-package-manager, dnf_packages: nmap }

License
-------

BSD

Author Information
------------------

The best way to reach out to me is through GH issues or ping me at [twitter](https://twitter.com/fr1t3).
