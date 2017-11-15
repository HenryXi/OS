# Linux no space left on device
If the message `No space left on device` appears that means you need clear the file on your system or add new disk for
your computer. "No space" not only means no free disk, it may also mean there is no iNodes in your system. 

Use `df -h` to show the space of your disk.
````bash
[root@virtual ~]$ df -h
Filesystem                      Size  Used Avail Use% Mounted on
/dev/mapper/vg_virtual-lv_root   50G  4.8G   42G  11% /
tmpfs                           939M  4.0K  939M   1% /dev/shm
/dev/sda1                       477M   28M  425M   7% /boot
/dev/mapper/vg_virtual-lv_home   45G   54M   43G   1% /home
````
Use `df -i` to show the iNodes info of your system.
```bash
[root@virtual ~]$ df -i
Filesystem                          Inodes IUsed   IFree IUse% Mounted on
/dev/mapper/vg_virtual-lv_root     3276800 57639 3219161    2% /
tmpfs                               240256     2  240254    1% /dev/shm
/dev/sda1                           128016    38  127978    1% /boot
/dev/mapper/vg_virtual-lv_home     2990080    14 2990066    1% /home
```

**Clear iNodes**

If there are too many small files in your system you can not create new file any more. Use the following commands to find
which directory contains too many files.
```bash
for i in /*; do echo $i; find $i |wc -l; done
```

EOF