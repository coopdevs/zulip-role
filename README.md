Zulip Role
=========

An ansible role to install Zulip using the [Zulip installer](https://zulip.readthedocs.io/en/stable/production/install.html).

The Zulip installer takes care of installing all dependencies and configure them.


Role Variables
--------------

```yaml
development_enviroment: false
host_name: example.com
email: example@example.com
ansible_installer: https://download.zulip.com/server/zulip-server-latest.tar.gz
ssl: ''
```

The `ssl` parameter is automatically configured based on the `development_enviroment` parameter. If there is already a valid SSL certificate, you must set it manually to an empty string. The valid values are either `''`, `--certbot` or `--self-signed`.

Example Playbook
----------------
Simply add the role to your provisioning playbook and pass it the `email` and `host_name` variables:

```bash
ansible-playbook tests/test.yml -i tests/inventory --extra-vars '{"email":"email@example.com", "host_name":"zulip.local", development_enviroment: true}'
```
License
-------

GPLv3

Author Information
------------------

[Coopdevs](https://coopdevs.org)