# Use top command in Linux
We often use top command to see the tasks in Linux. There are many numbers in the output of top. In this page I will
shortly introduce them. The output of top command is like following. 
```
top - 14:46:30 up 197 days, 20:44,  4 users,  load average: 0.05, 0.06, 0.02
Tasks: 103 total,   2 running, 101 sleeping,   0 stopped,   0 zombie
Cpu(s):  0.9%us,  0.0%sy,  0.0%ni, 98.7%id,  0.4%wa,  0.0%hi,  0.0%si,  0.0%st
Mem:   5993172k total,  5867316k used,   125856k free,   147540k buffers
Swap: 16777208k total,        0k used, 16777208k free,  3167192k cached

  PID USER      PR  NI  VIRT  RES  SHR S %CPU %MEM    TIME+  COMMAND                                                                                                                  
 6372 root      20   0 1780m  50m 1896 S 13.6  0.9 641:32.67 mqttmsg                                                                                                                   
30959 root      20   0 2880m 919m  14m S  1.7 15.7  12:27.13 java                                                                                                                      
24781 root      20   0 1611m 151m 2208 S  1.3  2.6  51:12.51 mqttmsg                                                                                                                   
 1430 root      20   0 1173m  11m 1240 S  1.0  0.2   1894:19 authserver                                                                                                                
 9765 root      20   0  850m 4584 1252 S  0.7  0.1 186:36.71 authserver                                                                                                                
    1 root      20   0 19232 1112  820 S  0.0  0.0   0:02.60 init                                                                                                                      
    2 root      20   0     0    0    0 S  0.0  0.0   0:00.00 kthreadd                                                                                                                  
    3 root      RT   0     0    0    0 S  0.0  0.0   0:03.49 migration/0                                                                                                               
    4 root      20   0     0    0    0 S  0.0  0.0   7:41.93 ksoftirqd/0                                                                                                               
    5 root      RT   0     0    0    0 S  0.0  0.0   0:00.00 migration/0                                                                                                               
    6 root      RT   0     0    0    0 S  0.0  0.0   0:10.21 watchdog/0                                                                                                                
    7 root      RT   0     0    0    0 S  0.0  0.0   0:04.88 migration/1                                                                                                               
    8 root      RT   0     0    0    0 S  0.0  0.0   0:00.00 migration/1                                                                                                               
    9 root      20   0     0    0    0 S  0.0  0.0  14:00.37 ksoftirqd/1                                                                                                               
   10 root      RT   0     0    0    0 S  0.0  0.0   0:11.88 watchdog/1                                                                                                                
   11 root      20   0     0    0    0 R  0.0  0.0  68:12.03 events/0                                                                                                                  
   12 root      20   0     0    0    0 S  0.0  0.0   5:05.46 events/1                                                                                                                  
   13 root      20   0     0    0    0 S  0.0  0.0   0:00.00 cgroup                                                                                                                    
   14 root      20   0     0    0    0 S  0.0  0.0   0:01.52 khelper                                                                                                                   
   15 root      20   0     0    0    0 S  0.0  0.0   0:00.00 netns                                                                                                                     
   16 root      20   0     0    0    0 S  0.0  0.0   0:00.00 async/mgr                                                                                                                 
   17 root      20   0     0    0    0 S  0.0  0.0   0:00.00 pm                                                                                                                        
   18 root      20   0     0    0    0 S  0.0  0.0   0:19.03 sync_supers                                                                                                               
   19 root      20   0     0    0    0 S  0.0  0.0   0:22.28 bdi-default                                                                                                               
   20 root      20   0     0    0    0 S  0.0  0.0   0:00.00 kintegrityd/0                                                                                                             
   21 root      20   0     0    0    0 S  0.0  0.0   0:00.00 kintegrityd/1                                                                                                             
   22 root      20   0     0    0    0 S  0.0  0.0   1:35.37 kblockd/0                                                                                                                 
   23 root      20   0     0    0    0 S  0.0  0.0   0:10.58 kblockd/1                                                                                                                 
   24 root      20   0     0    0    0 S  0.0  0.0   0:00.00 kacpid                                                                                                                    
   25 root      20   0     0    0    0 S  0.0  0.0   0:00.00 kacpi_notify                                                                                                              
   26 root      20   0     0    0    0 S  0.0  0.0   0:00.00 kacpi_hotplug                                                                                                             
   27 root      20   0     0    0    0 S  0.0  0.0   0:00.00 ata_aux                                                                                                                   
   28 root      20   0     0    0    0 S  0.0  0.0   0:00.00 ata_sff/0                                                                                                                 
   29 root      20   0     0    0    0 S  0.0  0.0   0:00.00 ata_sff/1                                                                                                                 
   30 root      20   0     0    0    0 S  0.0  0.0   0:00.00 ksuspend_usbd                                                                                                             
   31 root      20   0     0    0    0 S  0.0  0.0   0:00.00 khubd                                                                                                                     
   32 root      20   0     0    0    0 S  0.0  0.0   0:00.00 kseriod                                                                                                                   
   33 root      20   0     0    0    0 S  0.0  0.0   0:00.00 md/0                                                                                                                      
   34 root      20   0     0    0    0 S  0.0  0.0   0:00.00 md/1                                                                                                                      
   35 root      20   0     0    0    0 S  0.0  0.0   0:00.00 md_misc/0    
```
**First line**: this line shows this computer has been running 197 days 14 hours 46 minutes and 30 seconds. Maybe our computer won't
keep running for such long time. But for a server it might be running several years. The time now is `20:44`. `4 users` 
means there are 4 users are operating this computer. `load average` show how busy the CPU is (maybe there are more than
one CPUs in your environment). There are 3 numbers to show the load average in recent 1, 5 and 15 minutes. The smaller 
load average number means the lower resource usage.

**Second line**: this line shows the total tasks in this computer. How many tasks are running, sleeping or stopped right now?
Now, there are 103 tasks need to be handled, but only one task is running. Most tasks are sleeping.

**Third line**: This line shows the percentage of different kind of tasks use CPU. `0.9%us` means user program take
0.9% time of CPU. `0.4%wa` means IO take 0.4% time of CPU. `98.7%id` means 98.7% time of CPU is idle.

**Fourth line**: This line shows the memory usage. Total memory is 5993172k, 5867316k is used, and 125856k is free and 147540k in buffers.
If in Windows free memory remain 125856/5993172 = 2%, you have to close some programs or add more memory. But in Linux
is different from Windows. You can calculate the "free" memory in this way. Free memory = 125856k free + 147540k buffers + 3167192k cached
= 3440588k. The free memory remain 3440588/5993172=57.4%.

**Fifth line**:This line shows the usage of swap. OS will transfer some memory data which is not used recently to swap.
For more detail of swap size of CentOS click [here](https://www.centos.org/docs/5/html/Deployment_Guide-en-US/ch-swapspace.html).
If the size of used swap changes frequently means data is transferred between memory and swap frequently. You need add more memory to your server.

**The Rest**: Shows every process detail every line. You can get the memory used and CPU time used. If the used CPU
percentage larger than 100% means there are two CPUs or CPU cores in your computer and all of them are busy.