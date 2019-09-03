# Linux restart one network interface
Use following commands to restart on network interface. First you need to know that how many network cards on your machine.
```bash
ifconfig
[root@localhost ~]# ifconfig
enp0s3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.232.24.233  netmask 255.255.255.0  broadcast 10.232.24.255
        ether 08:00:27:3f:4d:9d  txqueuelen 1000  (Ethernet)
        RX packets 210791952  bytes 22194532411 (20.6 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 94766333  bytes 16999211753 (15.8 GiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

enp0s8: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.56.8  netmask 255.255.255.0  broadcast 192.168.56.255
        ether 08:00:27:20:c3:20  txqueuelen 1000  (Ethernet)
        RX packets 7298662  bytes 1464429877 (1.3 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 13032965  bytes 8945762415 (8.3 GiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        loop  txqueuelen 1  (Local Loopback)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```
If you want to restart `enp0s8` you can use `ifdown` and `ifup` commands.
```bash
ifdown enp0s3 && ifup enp0s3
```

EOF