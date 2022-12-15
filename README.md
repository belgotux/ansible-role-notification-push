notification-push
=================

Deploy one or more push notification scripts.
Currently supported scripts are :
- [pushbullet](https://github.com/belgotux/pushbullet-notification-linux)
- [telegram](https://github.com/belgotux/telegram-notification-linux)

Requirements
------------
Generate a token for at least one of the solution. Please see the link bellow for the readme.

Role Variables
--------------
- `notification_telegram_provider_api` : telegram provider API (default `https://api.telegram.org`)
- `notification_telegram_access_token` : telegram bot token
- `notification_telegram_chat_id` : telegram channel chat ID, you can set it, or a call is done to get it.
- `notification_pushbullet_provider_api` : pushbullet provider API (default `https://api.pushbullet.com/v2/pushes`)
- `notification_pushbullet_access_token` : pushbullet access token

Example Playbook
----------------

For pushbullet :
```
- hosts: servers
  roles:
      - { role: notification-push vars: notification_pushbullet_access_token: 'o.XXXXXXXXXXXXXXXXXXXXX' }
```

For telegram :
```
- hosts: servers
  roles:
      - { role: notification-push vars: notification_telegram_access_token: 'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX' }
```

License
-------

[GPL v3](https://www.gnu.org/licenses/gpl-3.0.en.html)

Author Information
------------------

Belgotux
[MonLinux](https://www.monlinux.net)
