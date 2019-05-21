CentOS Security Updates
==================

An Ansible Role that configures CentOS security updates, using the [Updateinfo](https://updateinfo.cefs.steve-meier.de/) 
repository - A yum repository with 
CentOS Errata information

Requirements
------------

Become a patron of the Updateinfo project on [Patreon](https://www.patreon.com/stevemeier). It's $1/month and will 
help run the site and pay for Amazon CloudFront which serves the content.

Role Variables
--------------

Available variables are listed below, along with default values (see 
`defaults/main.yml`):

    centos_security_updates_enabled: yes

Enable or disable the updates yum repository.

    centos_security_updates_file: CentOS-Errata
    
Name of the repository file stored in `/etc/yum.repos.d/`, default file will be saved as `CentOS-Errata.repo`.

    centos_security_updates_name: errata
    
Unique Repository ID used for the section name of the repository in the repo file.

     centos_security_updates_endpoint: updateinfo.cefs.steve-meier.de
     
Domain endpoint to the updates repository.

    centos_security_updates_email: you@example.com
    centos_security_updates_password: PASSWORD
    
Email address and password you received from `Steve Meier <email (at) steve (dash) meier (dot) de>` _(not your Patreon 
credentials)_.
    
    centos_security_updates_yum_update_cmd: security
    
Kind of updates to run via yum-cron (if enabled), e.g. `default`, `security`, `minimal` etc.

Dependencies
------------

- [geerlingguy.security](https://galaxy.ansible.com/geerlingguy/security/)

Example Playbook
----------------

    - hosts: all
      become: yes
      vars:
        - centos_security_updates_email: you@example.com
        - centos_security_updates_password: PASSWORD
      roles:
         - memiah.centos-security-updates

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2019 by [Memiah Limited](https://github.com/memiah).
