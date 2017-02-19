# Enable network after centos minimal install
The network is disabled after minimal install CentOS. You can use the following command to enable the network.
`service network start`. The network service does not start after rebooting the system. Change the config file to
make the network automatic start. The path of configuration file is `/etc/sysconfig/network-scripts/ifcfg-eth0`.
The content of configuration file is like following.
```
DEVICE=eth0
HWADDR=08:00:27:8B:09:1B
TYPE=Ethernet
UUID=a20ee594-de74-4561-bf9c-4ea98b24b124
ONBOOT=yes
NM_CONTROLLED=yes
BOOTPROTO=dhcp
```
Change `ONBOOT=yes` will make network automatic enable when boot the system.