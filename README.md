Zulip Role
=========

An ansible role to install Zulip using the [Zulip installer](https://zulip.readthedocs.io/en/stable/production/install.html).

The Zulip installer takes care of installing all dependencies and configure them.

This Ansible role is designed to check for the existence of any active Zulip realms before proceeding with the installation or update process. If an active realm is detected, the role will automatically update your Zulip installation to ensure compatibility and seamless integration with existing realms. This approach helps maintain the stability of your Zulip environment and minimizes potential disruptions to your users.


Role Variables
--------------

```yaml
development_enviroment: false
zulip_hostname: example.com
zulip_version: latest
zulip_installer: "https://download.zulip.com/server/zulip-server-{{ zulip_version }}.tar.gz"
cerbot_email: example@example.com
certbot_ssl: ''
zulip_push_notifications: true
zulip_push_bouncer_url: "https://push.zulipchat.com"
zulip_enable_mail: true
zulip_smtp_server:
zulip_sendmail_user:
zulip_sendmail_password:
zulip_enable_giphy: true
zulip_giphy_api_key:
```

The `certbot_ssl` parameter is automatically configured based on the `development_enviroment` parameter. If there is already a valid SSL certificate, you must set it manually to an empty string. The valid values are either `''`, `--certbot` or `--self-signed`. `cerbot_email` must be provided in order to issue a certificate request using certbot.

The `zulip_push_notifications` boolean parameter is used to enable or disable push notifications. If you want to use push notifications, you must set the `zulip_push_bouncer_url` parameter to the URL of your push bouncer. By default, it is set to the Zulip push bouncer URL (https://push.zulipchat.com).

The `zulip_enable_mail` boolean parameter is used to enable or disable email auto-configuration. If you want to use the email auto-configuration, you must set the `zulip_smtp_server`, `zulip_sendmail_user` and `zulip_sendmail_password` parameters.

The `zulip_enable_giphy` boolean parameter is used to enable or disable the Giphy integration. By default, it is set to `true`. If you want to use the Giphy integration, you must set the `zulip_giphy_api_key` parameter to the API key of your Giphy account.

Examples
-------
An implementation of this role can be found in the [`zulip-provisioning`](https://git.coopdevs.org/coopdevs/tooling/zulip-provisioning) repository.

License
-------

GPLv3

Author Information
------------------

[Coopdevs](https://coopdevs.org)
