# Ansible role that manages the Xonotic client and server on Linux

[Xonotic](https://xonotic.org) is The Free and Fast Arena Shooter.

Xonotic is an addictive, arena-style first person shooter with crisp movement and a wide array of weapons. It combines intuitive mechanics with in-your-face action to elevate your heart rate. Xonotic is and will always be free-to-play. It is available under the copyleft-style GPLv3+ license.

## Requirements

This module requires Ansible >=2.8 version.

## Mandatory role variables

The order of these variables counts in generating the data dynamically!

If the `xonotic_server` is set to `no` then the "Server only" part will be skipped,
the dedicated server will not be configured.

```
# Client & Server
xonotic_owner: tmolnar
xonotic_group: tmolnar
xonotic_version: 0.8.2
xonotic_extr_path: /home/{{ xonotic_owner }}/stuff/games
xonotic_binary: "{{ xonotic_extr_path }}/Xonotic/xonotic-linux64-glx"
xonotic_dl_url: https://dl.xonotic.org/xonotic-{{ xonotic_version }}.zip
xonotic_dl_path: /tmp/xonotic-{{ xonotic_version }}.zip
```

# Server only mandatory variables

If the `xonotic_server` is set to `yes`, then the following variables are mandatory as well.

```
# Server only
xonotic_server: yes
xonotic_sv_public: 1
xonotic_sv_status_privacy: 1
xonotic_hostname: Iron Arena $g_xonoticversion
xonotic_sv_motd: Hello, please be nice and enjoy the game! Good luck! :)
xonotic_maxplayers: 12
xonotic_port: 26000
xonotic_log_file: ${serverconfig}.log
g_start_delay: 10
g_maplist: "afterslime atelier boil catharsis courtfun dance drain erbium finalrage fuse geoplanetary glowplant implosion leave_em_behind nexballarena oilrig runningman runningmanctf silentsiege solarium space-elevator stormkeep techassault vorix warfare xoylent"
g_maplist_shuffle: 1
g_maplist_mostrecent_count: 3
gametype: dm
```

## Optional role variables
```
timelimit_override: -1
fraglimit_override: -1
capturelimit_override: -1
g_domination_point_limit: -1
g_keyhunt_point_limit: -1
g_lms_lives_override: -1
g_nexball_goallimit: -1
g_ctf_ignore_frags: 1
g_keyhunt_teams_override: -1
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
