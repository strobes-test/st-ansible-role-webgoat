Ansible Role: Webgoat
=========

Build status for this role: [![Build Status](https://travis-ci.org/PeterMosmans/ansible-role-webgoat.svg)](https://travis-ci.org/PeterMosmans/ansible-role-webgoat)


This role downloads, configures and installs the OWASP WebGoat service.


Requirements
------------

Make sure that traffic to port 8080 tcp is allowed, as that's the port where WebGoat will be listening on.


Role Variables
--------------
Available variables are listed below, along with default values. The default values are specified in `default/main.yml`.

```
webgoat_base: /var/www/webgoat
webgoat_group: webgoat
webgoat_url: https://github.com/WebGoat/WebGoat/releases/download/7.1/webgoat-container-7.1-exec.jar
webgoat_user: webgoat
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
    - role: PeterMosmans.webgoat
      tags: webgoat
```
This example will install WebGoat to `/var/www/webgoat`, and automatically start the service upon boot, as user `webgoat`.


License
-------

GPLv3


Author Information
------------------

Created by Peter Mosmans. Suggestions, feedback and pull requests are always welcome.
