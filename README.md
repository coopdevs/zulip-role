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
zulip_push_notifications: true
zulip_push_bouncer_url: "https://push.zulipchat.com"
zulip_enable_mail: true
zulip_smtp_server:
zulip_email_user:
zulip_email_password:
zulip_enable_giphy: true
zulip_giphy_api_key: 
```

The `ssl` parameter is automatically configured based on the `development_enviroment` parameter. If there is already a valid SSL certificate, you must set it manually to an empty string. The valid values are either `''`, `--certbot` or `--self-signed`.

The `zulip_push_notifications` boolean parameter is used to enable or disable push notifications. If you want to use push notifications, you must set the `zulip_push_bouncer_url` parameter to the URL of your push bouncer. By default, it is set to the Zulip push bouncer URL (https://push.zulipchat.com).

The `zulip_enable_mail` boolean parameter is used to enable or disable email auto-configuration. If you want to use the email auto-configuration, you must set the `zulip_smtp_server`, `zulip_email_user` and `zulip_email_password` parameters.

The `zulip_enable_giphy` boolean parameter is used to enable or disable the Giphy integration. By default, it is set to `true`. If you want to use the Giphy integration, you must set the `zulip_giphy_api_key` parameter to the API key of your Giphy account.

License
-------

GPLv3

Author Information
------------------

[Coopdevs](https://coopdevs.org)