klems.crontabs
=========
[![Build Status](https://travis-ci.org/klems/ansible-role-crontabs.svg?branch=master)](https://travis-ci.org/klems/ansible-role-crontabs)

A role to confgiure crontabs

Requirements
------------
Ansible == `2.4`

Role Variables
--------------
### {{ crontabs }}

A list of crontabs to be configured :

```
crontabs:
  - cron_name: "rsync"
    month: "*"
    weekday: "*"
    day: "*"
    minute: "*/60"
    hour: "*"
    user: "root"
    env: "no"
    env_name: ""
    env_value: ""
    job: "rsync -av /mnt/hdd-01/ /mnt/hdd-02/"
    cron_file: "hourly_rsync"
  - cron_name: "action"
    month: "*"
    weekday: "*"
    day: "*"
    minute: "*/5"
    hour: "9-18"
    user: "app_user"
    env: "yes"
    env_name: "ENV"
    env_value: "PRODUCTION"
    job: "sudo /srv/myapp/super_script.py >> /var/log/myapp/super_script.log"
    cron_file: "app_script"
```

Dependencies
------------
N/A

Example Playbook
----------------

```
- hosts: servers
  roles:
     - { role: klems.crontabs }
```

License
-------
BSD

Author Information
------------------
mail: klems@klems.net
