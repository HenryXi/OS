# Monitor IO in Linux
There are a lot of tool to monitor IO in Linux. `iotop` is one of the most common command to monitor IO of each process.
`iostat` is another common commands. I will show you how to use them in this blog. 

**iotop**

The output of it is like following.
```
Total DISK READ: 0.00 B/s | Total DISK WRITE: 364.42 K/s
  TID  PRIO  USER     DISK READ  DISK WRITE  SWAPIN     IO>    COMMAND                                                                                                                 
 9789 be/4 root        0.00 B/s    7.29 K/s  0.00 % 32.54 % java -Djava.util.logging.config.file=/opt/web_app/tomcat_sdpk~at_sdpk_8084/temp org.apache.catalina.startup.Bootstrap start
  357 be/3 root        0.00 B/s   61.95 K/s  0.00 % 20.02 % [jbd2/sda3-8]
 3404 be/4 root        0.00 B/s    3.64 K/s  0.00 %  0.00 % java -Djava.util.logging.config.file=/opt/web_app/tomcat_file~at_file_8082/temp org.apache.catalina.startup.Bootstrap start
 1391 be/4 root        0.00 B/s    7.29 K/s  0.00 %  0.00 % [flush-8:0]
25723 be/4 root        0.00 B/s    7.29 K/s  0.00 %  0.00 % java -Djava.util.logging.config.file=/opt/web_app/tomcat_hd_8~mcat_hd_8189/temp org.apache.catalina.startup.Bootstrap start
    1 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % init
    2 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [kthreadd]
    3 rt/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [migration/0]
    4 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [ksoftirqd/0]
    5 rt/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [stopper/0]
    6 rt/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [watchdog/0]
    7 rt/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [migration/1]
    8 rt/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [stopper/1]
    9 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [ksoftirqd/1]
   10 rt/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [watchdog/1]
   11 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [events/0]
   12 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [events/1]
   13 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [events/0]
   14 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [events/1]
   15 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [events_long/0]
   16 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [events_long/1]
   17 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [events_power_ef]
   18 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [events_power_ef]
   19 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [cgroup]
   20 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [khelper]
   21 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [netns]
   22 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [async/mgr]
   23 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [pm]
   24 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [sync_supers]
   25 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [bdi-default]
   26 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [kintegrityd/0]
   27 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [kintegrityd/1]
   28 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [kblockd/0]
   29 be/4 root        0.00 B/s    0.00 B/s  0.00 %  0.00 % [kblockd/1]
```
There are a lot of processes do not read or write. If you want it only show the processes doing I/O use this command
like this `iotop -o`. If you want monitor the specify process use it like this `iotop -p 9789`.

**iostat**

This command is different from `iotop` it will show you the overview of IO instead of every process's. The output of
it is like following.
```
Linux 2.6.32-573.22.1.el6.x86_64 (localhost.localdomain) 	09/30/2016 	_x86_64_	(2 CPU)

avg-cpu:  %user   %nice %system %iowait  %steal   %idle
           2.36    0.00    0.44    2.22    0.00   94.97

Device:            tps   Blk_read/s   Blk_wrtn/s   Blk_read   Blk_wrtn
sda               8.73       138.39       196.54  242392164  344226556
```
It display the IO status in block by default, if you want it display in kilobytes use this command like this `iostat -k`. (`iotop`
display the IO status in kilobytes by default.) We can use `-x` parameter to show extended IO information. The output of 
`iostat -x -k` is like following.
```
Linux 2.6.32-573.22.1.el6.x86_64 (localhost.localdomain) 	09/30/2016 	_x86_64_	(2 CPU)

avg-cpu:  %user   %nice %system %iowait  %steal   %idle
           2.36    0.00    0.44    2.22    0.00   94.97

Device:         rrqm/s   wrqm/s     r/s     w/s    rkB/s    wkB/s avgrq-sz avgqu-sz   await  svctm  %util
sda               0.96    18.02    2.19    6.54    69.18    98.25    38.35     0.25   28.47   5.91   5.16
```
"%util" in the far right of the output means the usage of this disk. 5.16% is very low for the single disk computer.
If this value is larger than 100% in the single disk computer that means IO is busy now. If there are many disk in your
 computer this value may larger than 100% but that may not mean IO is busy.