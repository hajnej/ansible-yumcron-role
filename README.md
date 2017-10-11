ansible-yumcron-role
=========

Ansible role to install and configure yum-cron package - tool for checking and applying OS updates

Requirements
------------

There is no requirements for this role

Role Variables
--------------

All variables are used to render `/etc/yum/yum-cron.conf` and `/etc/yum/yum-cron-hourly.conf`. Those variables respect yum-cron.conf configuration options. By default hourly updates are enabled and applied and report is sent via stdio. Daily updates are disabled because they are useless for this settings.

    yumcron_update_messages_hourly: "yes"
    yumcron_download_updates_hourly: "yes"
    yumcron_apply_updates_hourly: "yes"
    yumcron_emit_via_hourly: "stdio"
    yumcron_email_to_hourly: "root"

    yumcron_update_cmd: "default"
    yumcron_update_messages: "no"
    yumcron_download_updates: "no"
    yumcron_apply_updates: "no"
    yumcron_emit_via: "stdio"
    yumcron_email_to: "root"

Dependencies
------------

There is no dependencies for this role

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: ansible-yumcron-role, yumcron_emit_via_hourly: "email", yumcron_email_to_hourly: "user@example.com" }

License
-------

BSD

Author Information
------------------

Jakub Slatinsky, slatinskyj@gmail.com
