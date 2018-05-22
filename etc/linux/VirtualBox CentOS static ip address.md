# VirtualBox CentOS static ip address
I install CentOS in virtualBox and I use `Bridged Networking` to connect internet. Virtual machine is like a real machine 
in `bridged networking` mode. The problem is that when I restart virtual machine the ip will be changed. I have to use ssh to reconnect 
virtual machine(CentOS). To solve this problem I add another network adapter in virtual machine with `Host only` mode. Finally,
I can connect virtual machine by static ip address.

**add another network adapter**

`virtual machine settings -> Network -> Adapter2 -> Attached to (choose Host-only Adapter) -> Name (select default Adapter) -> OK`

Restart the virtual machine and copy `/etc/sysconfig/network-scripts/ifcfg-eth0` as `/etc/sysconfig/network-scripts/ifcfg-eth1`.
Change the content of `ifcfg-eth1` as following. 
```
DEVICE=eth1 
HWADDR=08:00:27:25:9B:F6
TYPE=Ethernet
UUID=8babba79-b455-4945-a855-82e187c48d1b
ONBOOT=yes
NM_CONTROLLED=yes
BOOTPROTO=static
IPADDR=192.168.56.6
NETMASK=255.255.255.0
```
* DEVICE: change the device name to `eth1`
* HWADDR: You can find the address in `virtual machine settings -> Network -> Adapter2 -> Advanced`
* BOOTPROTO: change `dhcp` to `static`, we will connect this virtual machine by static ip.
* IPADDR: choose the static ip address you like. The default network segment of `Host-only` adapter in VirtualBox(5.2.12) is `192.168.56.*`
* NETMASK: use `255.255.255.0`

**restart the network service**
```bash
[root@virtual ~]# service network restart
Shutting down interface eth0:                              [  OK  ]
Shutting down interface eth1:                              [  OK  ]
Shutting down loopback interface:                          [  OK  ]
Bringing up loopback interface:                            [  OK  ]
Bringing up interface eth0:  
Determining IP information for eth0... done.
                                                           [  OK  ]
Bringing up interface eth1:  Determining if ip address 192.168.56.6 is already in use for device eth1...
                                                           [  OK  ]
[root@virtual ~]# ifconfig
eth0      Link encap:Ethernet  HWaddr 08:00:27:1D:55:3D  
          inet addr:10.232.22.210  Bcast:10.232.22.255  Mask:255.255.255.0
          inet6 addr: fe80::a00:27ff:fe1d:553d/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:4597 errors:0 dropped:0 overruns:0 frame:0
          TX packets:90 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:339004 (331.0 KiB)  TX bytes:9411 (9.1 KiB)

eth1      Link encap:Ethernet  HWaddr 08:00:27:25:9B:F6  
          inet addr:192.168.56.6  Bcast:192.168.56.255  Mask:255.255.255.0
          inet6 addr: fe80::a00:27ff:fe25:9bf6/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:809 errors:0 dropped:0 overruns:0 frame:0
          TX packets:747 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:71659 (69.9 KiB)  TX bytes:85144 (83.1 KiB)

lo        Link encap:Local Loopback  
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:299 errors:0 dropped:0 overruns:0 frame:0
          TX packets:299 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0 
          RX bytes:26689 (26.0 KiB)  TX bytes:26689 (26.0 KiB)
```

Now you can connect virtual machine by this ip(192.168.56.6) and it won't be changed after restarting.

EOF 