# Creating a `systemctl` service
Creating a service with `systemctl` can be used to run a program at system startup and can restart
the program if it exits.

To create a service, just create a file in `/usr/lib/systemd/system/` named <service-name>.service
(example: my-server.service).

Below is an example of a unit file;
```text
[Unit]
Description=Example unit file
After=auditd.service systemd-user-sessions.service time-sync.target autofs.service
 
[Service]
User=username
TimeoutStartSec=0
Type=simple
KillMode=process
WorkingDirectory=/home/username/server
ExecStart=/usr/bin/python3 server.py
Restart=always
RestartSec=2
LimitNOFILE=5555
 
[Install]
WantedBy=multi-user.target
```

---

## Further reading

For more information, please see this article:
[https://opensource.com/article/20/5/systemd-units](
https://opensource.com/article/20/5/systemd-units)