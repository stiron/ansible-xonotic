# Ansible module that installs and configures the Xonotic server

## Requirements

This module requires Ansible >=2.9 version.

## Role variables
```
vars:
    # Client & Server
    - xonotic_owner: tmolnar
    - xonotic_group: tmolnar
    - xonotic_version: 0.8.2
    - xonotic_extr_path: /home/{{ xonotic_owner }}/stuff/games
    - xonotic_binary: "{{ xonotic_extr_path }}/Xonotic/xonotic-linux64-glx"
    - xonotic_dl_url: https://dl.xonotic.org/xonotic-{{ xonotic_version }}.zip
    - xonotic_dl_path: /tmp/xonotic-{{ xonotic_version }}.zip
    # Server only
    - xonotic_server: yes
    - xonotic_sv_public: 1
    - xonotic_sv_status_privacy: 1
    - xonotic_hostname: Iron Arena $g_xonoticversion
    - xonotic_sv_motd: Hello, please be nice and enjoy the game! Good luck! :)
    - xonotic_maxplayers: 12
    - xonotic_port: 26000
    - xonotic_log_file: ${serverconfig}.log
    - g_start_delay: 10
    - g_maplist: "afterslime atelier boil catharsis courtfun dance drain erbium finalrage fuse geoplanetary glowplant implosion leave_em_behind nexballarena oilrig runningman runningmanctf silentsiege solarium space-elevator stormkeep techassault vorix warfare xoylent"
    - g_maplist_shuffle: 1
    - g_maplist_mostrecent_count: 3
    - gametype: dm
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
