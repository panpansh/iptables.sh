# iptables.sh

```bash
curl --url https://raw.githubusercontent.com/panpansh/iptables.sh/master/firewall --output /etc/init.d/firewall
curl --url https://raw.githubusercontent.com/panpansh/iptables.sh/master/firewall-noip --output /etc/init.d/firewall-noip
chmod +x /etc/init.d/firewall
chmod +x /etc/init.d/firewall-noip
```

Edit /etc/init.d/firewall and /etc/init.d/firewall-noip to match your needs

```bash
/etc/init.d/firewall
# check rules
/sbin/iptables -L
```

When you are satisfied with the rules add them to sysvinit

```bash
/sbin/update-rc.d firewall defaults
```

Add /etc/init.d/firewall-noip to crontab
```bash
*/20 * * * * /etc/init.d/firewall-noip
```
in this case the script run every 20 minutes

You are welcome to make changes.
