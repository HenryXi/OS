# Count the number of output lines in Linux
If the output or a text file is not too long we can know how many lines. But sometimes the output is 
to long to show them in one screen. At this point you need `wc` command to count the numbers of output
lines. For example there are many log files like following.
```bash
[root@localhost log]# ll
total 234328
-rw-r--r-- 1 root root        0 May 23 13:56 access.log
-rw-r--r-- 1 root root        0 May 23 13:56 error.log
-rw-r--r-- 1 root root        0 May 23 13:56 external.log
-rw-r--r-- 1 root root    50582 Jun 16 11:02 info.log
-rw-r--r-- 1 root root    14579 May 23 14:11 info.log.2016-05-23
-rw-r--r-- 1 root root     8699 May 24 10:24 info.log.2016-05-24
-rw-r--r-- 1 root root   204397 May 25 19:32 info.log.2016-05-25
-rw-r--r-- 1 root root  1672696 May 26 20:07 info.log.2016-05-26
-rw-r--r-- 1 root root     9147 May 27 15:55 info.log.2016-05-27
-rw-r--r-- 1 root root  2696198 May 28 21:29 info.log.2016-05-28
-rw-r--r-- 1 root root  6937430 May 30 23:46 info.log.2016-05-30
-rw-r--r-- 1 root root  5117172 May 31 21:10 info.log.2016-05-31
-rw-r--r-- 1 root root  5066278 Jun  1 22:42 info.log.2016-06-01
-rw-r--r-- 1 root root 15548054 Jun  2 23:57 info.log.2016-06-02
-rw-r--r-- 1 root root  5348536 Jun  3 22:04 info.log.2016-06-03
-rw-r--r-- 1 root root 22020182 Jun  4 22:14 info.log.2016-06-04
-rw-r--r-- 1 root root 35066747 Jun  6 22:43 info.log.2016-06-06
-rw-r--r-- 1 root root 71681271 Jun  7 23:42 info.log.2016-06-07
-rw-r--r-- 1 root root 30729998 Jun  8 23:59 info.log.2016-06-08
-rw-r--r-- 1 root root    48426 Jun  9 00:57 info.log.2016-06-09
-rw-r--r-- 1 root root    45870 Jun 11 11:11 info.log.2016-06-11
-rw-r--r-- 1 root root  6397876 Jun 12 20:43 info.log.2016-06-12
-rw-r--r-- 1 root root 14144587 Jun 13 23:57 info.log.2016-06-13
-rw-r--r-- 1 root root 12854805 Jun 14 20:31 info.log.2016-06-14
-rw-r--r-- 1 root root  4182759 Jun 15 16:07 info.log.2016-06-15
-rw-r--r-- 1 root root        0 May 23 13:56 MonthTaskService.log
-rw-r--r-- 1 root root        0 May 23 13:56 performance.log

```
Let's count the number of log files.
```bash
[root@localhost mallUserGoodsService]# ll | wc -l
28
```
**detail of `wc` command**

`wc` means word count. You can use it to count the number of words or the line number.

* -c count the byte
* -m count the character
* -l count the line
* -w count the words

examples are here
```bash
[root@localhost log]# cat wc_test.txt
This is a test file
test the wc command
wc can count the words, number of lines
[root@localhost log]# wc wc_test.txt 
3 17 80 wc_test.txt
[root@localhost log]# wc wc_test.txt -l
3 wc_test.txt
[root@localhost log]# wc wc_test.txt -w
17 wc_test.txt
[root@localhost log]# wc wc_test.txt -c
80 wc_test.txt
```

