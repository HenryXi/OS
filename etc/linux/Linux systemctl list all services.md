# Linux systemctl list all services
Use follow command to list all services in CentOS7. 
```
[root@virtual ~]# systemctl list-unit-files
UNIT FILE                                     STATE   
proc-sys-fs-binfmt_misc.automount             static  
dev-hugepages.mount                           static  
dev-mqueue.mount                              static  
proc-sys-fs-binfmt_misc.mount                 static  
sys-fs-fuse-connections.mount                 static  
......
......
chrony-dnssrv@.timer                          disabled
fstrim.timer                                  disabled
systemd-readahead-done.timer                  indirect
systemd-tmpfiles-clean.timer                  static  

239 unit files listed.
```

EOF