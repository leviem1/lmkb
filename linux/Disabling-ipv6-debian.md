# Disabling IPv6 in Debian 10/11

To disable IPv6 in Debian 10/11, edit the file `/etc/sysctl.conf` and add the following line:
```text
net.ipv6.conf.all.disable_ipv6 = 1
```

To apply the changes, run
```bash
sudo sysctl -p
```
