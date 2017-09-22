gocollect-playbook
=========

Ansible playbook which installs GoCollect, a tool which collects system info
and publishes it to a central server.
https://github.com/ossobv/gocollect

Starting from GoCollect version 0.6.0, GoCollect now supports core.meta
config files in the form of yaml. Ansible will copy over all template configs
in templates/core.meta, so make sure you add any custom core.meta config there!
For more info about the core.meta config check the GoCollect README.

Requirements
------------

None.

Role Variables
--------------

The following variables can be configured:
- `gocollect.api_key`
- `gocollect.register_url`
- `gocollect.push_url`
- `gocollect.collectors_path`
- `gocollect.include_path`

Note: previous version included `gocollect.install_hardware` because it wasn't
able to detect openstack based servers as guests. This seems to no longer be
the case and therefore the variable has been removed.

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
