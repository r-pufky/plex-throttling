**Deprecated**

This is now integrated into plex media server as a configuration option.

plex-throttling script for linux.

Original base code from this forum post:
  https://forums.plex.tv/discussion/39823/howto-limit-plex-media-server-bandwidth-on-linux


Installing
----------
place in /etc/init.d

```bash
sudo update-rc.d plex-throttling defaults
```

Tips
----
show TC rules
```bash
/sbin/tc -s -d class show dev eth0
```

Show iptables mangle rules
```bash
/sbin/iptables -t mangle -n -v -L
```

Show actual bandwidth being used on 32400
```bash
watch -n 1 /sbin/tc -s -d class show dev eth0
```

References:
http://www.cyberciti.biz/faq/linux-traffic-shaping-using-tc-to-control-http-traffic/
