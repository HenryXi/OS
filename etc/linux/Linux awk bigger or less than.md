# Linux awk bigger or less than
Let's say you have a file which contains log content. `awk` command can help you split every line of it and print the field 
you care about. `awk` can do more than this. Let's say your log file might look like this.
```
INFO 2018-04-27 00:00:00 version=2.5.3 time_cost=10
INFO 2018-04-27 00:00:00 version=2.5.3 time_cost=18
INFO 2018-04-27 00:00:01 version=2.5.2 time_cost=39
INFO 2018-04-27 00:00:01 version=2.5.2 time_cost=8
INFO 2018-04-27 00:00:14 version=2.5.3 time_cost=94
INFO 2018-04-27 00:00:14 version=2.5.3 time_cost=106
INFO 2018-04-27 00:00:26 version=2.5.2 time_cost=83
INFO 2018-04-27 00:00:26 version=2.5.2 time_cost=37
INFO 2018-04-27 00:00:30 version=2.5.3 time_cost=58
```
You can only print time_cost field by using following command.
```bash
[henry@virtual ~]$ cat log_file |awk '{print$5}'
time_cost=10
time_cost=18
time_cost=39
time_cost=8
time_cost=94
time_cost=106
time_cost=83
time_cost=37
time_cost=58
```
Print the time cost bigger than 50.
```bash
[henry@virtual ~]$ cat log_file |awk -F 'time_cost=' '$2>50 {print}'
INFO 2018-04-27 00:00:14 version=2.5.3 time_cost=94
INFO 2018-04-27 00:00:14 version=2.5.3 time_cost=106
INFO 2018-04-27 00:00:26 version=2.5.2 time_cost=83
INFO 2018-04-27 00:00:30 version=2.5.3 time_cost=58
```
Print the time cost less than 50.
```bash
[henry@virtual ~]$ cat log_file |awk -F 'time_cost=' '$2<50 {print}'
INFO 2018-04-27 00:00:00 version=2.5.3 time_cost=10
INFO 2018-04-27 00:00:00 version=2.5.3 time_cost=18
INFO 2018-04-27 00:00:01 version=2.5.2 time_cost=39
INFO 2018-04-27 00:00:01 version=2.5.2 time_cost=8
INFO 2018-04-27 00:00:26 version=2.5.2 time_cost=37
```
Print the time cost bigger than 50 and less than 100.
```bash
[henry@virtual ~]$ cat log_file |awk -F 'time_cost=' '$2>50 && $2<100 {print}'
INFO 2018-04-27 00:00:14 version=2.5.3 time_cost=94
INFO 2018-04-27 00:00:26 version=2.5.2 time_cost=83
INFO 2018-04-27 00:00:30 version=2.5.3 time_cost=58
```

EOF