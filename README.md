Zulip Role
=========

An ansible role to install Zulip using the [Zulip installer](https://zulip.readthedocs.io/en/stable/production/install.html).

The Zulip installer takes care of installing all dependencies and configure them.


Role Variables
--------------

```yaml
host_name: example.com
email: example@example.com
ansible_installer: https://download.zulip.com/server/zulip-server-latest.tar.gz
```


Example Playbook
----------------
Simply add the role to your provisioning playbook and pass it the `email` and `host_name` variables:

```bash
ansible-playbook tests/test.yml -i tests/inventory --extra-vars '{"email":"email@example.com", "host_name":"example.com"}'
```
License
-------

GPLv3

Author Information
------------------

[Coopdevs](https://coopdevs.org)