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

Note for Telegram : if you encounter an error like this follow, it's because you use your chat a long time ago, you need to send a message to the chat : 
```
TASK [notification-push : Call the api to get xml response with chat ID] ************************************************************************************************************************fatal: [host]: FAILED! => {"access_control_allow_methods": "GET, POST, OPTIONS", "access_control_allow_origin": "*", "access_control_expose_headers": "Content-Length,Content-Type,Date,Server,Connection", "changed": false, "connection": "close", "content": "{\"ok\":true,\"result\":[]}", "content_length": "23", "content_type": "application/json", "cookies": {}, "cookies_string": "", "date": "Mon, 27 Mar 2023 08:22:05 GMT", "elapsed": 0, "failed_when_result": true, "json": {"ok": true, "result": []}, "msg": "OK (23 bytes)", "redirected": false, "server": "nginx/1.18.0", "status": 200, "strict_transport_security": "max-age=31536000; includeSubDomains; preload", "url": "https://api.telegram.org/botxxxxxxxxx/getUpdates"}
```

License
-------

[GPL v3](https://www.gnu.org/licenses/gpl-3.0.en.html)

Author Information
------------------

Belgotux
[MonLinux](https://www.monlinux.net)
