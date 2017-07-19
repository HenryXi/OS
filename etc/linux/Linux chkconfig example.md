# Linux chkconfig example
`chkconfig` command can help you check or update the services installed in your environment. Let's say you have installed 
postgreSQL in your Linux. The script named "postgresql" will be installed in the directory "/etc/init.d/". `chkconfig` or
 `chkconfig --list` will output the services status like following.
```
auditd         	0:off	1:off	2:on	3:on	4:on	5:on	6:off
blk-availability	0:off	1:on	2:on	3:on	4:on	5:on	6:off
crond          	0:off	1:off	2:on	3:on	4:on	5:on	6:off
ip6tables      	0:off	1:off	2:on	3:on	4:on	5:on	6:off
iptables       	0:off	1:off	2:off	3:off	4:off	5:off	6:off
iscsi          	0:off	1:off	2:off	3:on	4:on	5:on	6:off
iscsid         	0:off	1:off	2:off	3:on	4:on	5:on	6:off
jexec          	0:off	1:on	2:on	3:on	4:on	5:on	6:off
lvm2-monitor   	0:off	1:on	2:on	3:on	4:on	5:on	6:off
mdmonitor      	0:off	1:off	2:on	3:on	4:on	5:on	6:off
messagebus     	0:off	1:off	2:on	3:on	4:on	5:on	6:off
multipathd     	0:off	1:off	2:off	3:off	4:off	5:off	6:off
mysqld         	0:off	1:off	2:off	3:off	4:off	5:off	6:off
netconsole     	0:off	1:off	2:off	3:off	4:off	5:off	6:off
netfs          	0:off	1:off	2:off	3:on	4:on	5:on	6:off
network        	0:off	1:off	2:on	3:on	4:on	5:on	6:off
nginx          	0:off	1:off	2:off	3:off	4:off	5:off	6:off
postfix        	0:off	1:off	2:on	3:on	4:on	5:on	6:off
postgresql     	0:off	1:off	2:on	3:on	4:on	5:on	6:off
rdisc          	0:off	1:off	2:off	3:off	4:off	5:off	6:off
restorecond    	0:off	1:off	2:off	3:off	4:off	5:off	6:off
rsyslog        	0:off	1:off	2:on	3:on	4:on	5:on	6:off
saslauthd      	0:off	1:off	2:off	3:off	4:off	5:off	6:off
sshd           	0:off	1:off	2:on	3:on	4:on	5:on	6:off
udev-post      	0:off	1:on	2:on	3:on	4:on	5:on	6:off
vboxadd        	0:off	1:off	2:on	3:on	4:on	5:on	6:off
vboxadd-service	0:off	1:off	2:on	3:on	4:on	5:on	6:off
vboxadd-x11    	0:off	1:off	2:off	3:on	4:off	5:on	6:off

```
6 columns in the output represent 6 levels.
```
0   Halt
1   Single-User mode
2   Multi-user mode console logins only (without networking)
3   Multi-User mode, console logins only
4   Not used/User-definable
5   Multi-User mode, with display manager as well as console logins (X11)
6   Reboot
```
For example, `postgresql    0:off	1:off	2:on	3:on	4:on	5:on	6:off` means service will be start 
when user login the system.
```bash
chkconfig postgresql on # make postgresql service start when user login
chkconfig postgresql off # make postgresql service don't start when user login
```

EOF