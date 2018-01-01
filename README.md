# Ansible module that installs and configures the Xonotic server

## Requirements

This module requires Ansible >=2.2 version.

## Role variables

```
# Task configuration
xonotic_dl_url: http://dl.xonotic.org/xonotic-0.8.2.zip
xonotic_dl_path: /tmp/xonotic.zip
xonotic_extr_path: /home/tmolnar/stuff/games
xonotic_owner: tmolnar
xonotic_group: tmolnar

# Template configuration for the server
xonotic_public: 1
xonotic_privacy: 1
xonotic_hostname: "Tom Ironman's Club"
xonotic_motd: "Hi to you!"
xonotic_maxplayers: 8
xonotic_port: 26000
xonotic_log_file: xonotic_server.log
xonotic_gametype: dm
```

## Examples

```
- hosts: xonotic-servers
  roles:
    - { role: xonotic }
```

## Dependencies

none

## License

MIT

## Author

Tamas Molnar - <tmolnar0831@gmail.com>
