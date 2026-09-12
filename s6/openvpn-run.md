# run

I customized the startup script for `openvpn` to avoid running the process as the root user, using `setpriv` to set necessarily caps and `uid:gid` as `openvpn:network`

```
#!/bin/execlineb -P

fdmove -c 1 2

setpriv --reuid=openvpn --regid=network --init-groups
  --inh-caps=-all,+net_admin --ambient-caps=-all,+net_admin
  --bounding-set=-all,+net_admin

exec /usr/bin/openvpn --config /etc/openvpn/openvpn.conf
```
