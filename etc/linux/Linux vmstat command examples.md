# Linux vmstat command examples
`vmstat` is used to report virtual memory statistics. We generally use it like this.
```
[work@virtual ~]$ vmstat 3 -w
procs -----------------------memory---------------------- ---swap-- -----io---- -system-- --------cpu--------
 r  b         swpd         free         buff        cache   si   so    bi    bo   in   cs  us  sy  id  wa  st
 2  0            0      3497044       583200     42296648    0    0     0    17    0    1   1   0  99   0   0
 0  0            0      3495268       583200     42297024    0    0     0    67 13669 15392   1   0  99   0   0
 0  0            0      3490848       583200     42297388    0    0     0   107 14469 16270   1   0  99   0   0
```
The number 3 after `vmstat` means output every 3 seconds. `-w` means enlarging field width.

The following is the meaning of each column. You can get more information from the manual.
```
Procs
   r: The number of processes waiting for run time.
   b: The number of processes in uninterruptible sleep.

Memory
   swpd: the amount of virtual memory used.
   free: the amount of idle memory.
   buff: the amount of memory used as buffers.
   cache: the amount of memory used as cache.
   inact: the amount of inactive memory. (-a option)
   active: the amount of active memory. (-a option)

Swap
   si: Amount of memory swapped in from disk (/s).
   so: Amount of memory swapped to disk (/s).

IO
   bi: Blocks received from a block device (blocks/s).
   bo: Blocks sent to a block device (blocks/s).

System
   in: The number of interrupts per second, including the clock.
   cs: The number of context switches per second.

CPU
   These are percentages of total CPU time.
   us: Time spent running non-kernel code. (user time, including nice time)
   sy: Time spent running kernel code. (system time)
   id: Time spent idle. Prior to Linux 2.5.41, this includes IO-wait time.
   wa: Time spent waiting for IO. Prior to Linux 2.5.41, included in idle.
   st: Time stolen from a virtual machine. Prior to Linux 2.6.11, unknown.
```

EOF