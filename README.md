gocollect-playbook
=========

Ansible playbook which installs GoCollect, a tool which collects system info and publishes it to a central server.
https://github.com/ossobv/gocollect

Requirements
------------

None.

Role Variables
--------------

Please configure the following variables:

- gocollect.api_key (not required)
- gocollect.register_url
- gocollect.push_url

If these are not set, the playbook will use the defaults!

Dependencies
------------

None.

Example Playbook
----------------

```
- hosts: all
  vars:
    gocollect:
      register_url: https://overridden.gocollect.example.com/client/v1/register/
      push_url: https://overridden.gocollect.example.com/client/v1/update/{regid}/{_collector}/
  roles:
    - ossobv.gocollect-playbook
```

License
-------

GNU GPLv3

Author Information
------------------

Jordi de Wal | OSSO B.V. <jdwal@osso.nl>
