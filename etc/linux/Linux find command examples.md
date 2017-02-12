# Linux find command examples
`find` is a very useful command when you want "find" something in Linux. In the page I will learn the basic use of
this command with you. For the detail of `find` you can learn from manual(type `man find` in command line).

* find by name
```bash
[root@web_server home]# find / -name java
/usr/java
/usr/java/jdk1.7.0_79/jre/bin/java
/usr/java/jdk1.7.0_79/bin/java
/usr/bin/java
/etc/pki/ca-trust/extracted/java
/etc/pki/java
[root@web_server home]# find / -name *ava
/usr/java
/usr/java/jdk1.7.0_79/jre/bin/java
/usr/java/jdk1.7.0_79/bin/java
/usr/share/zoneinfo/posix/Europe/Bratislava
/usr/share/zoneinfo/Europe/Bratislava
/usr/share/zoneinfo/right/Europe/Bratislava
/usr/bin/java
/etc/.java
/etc/pki/ca-trust/extracted/java
/etc/pki/java
[root@web_server home]# find / -iname Java
/usr/java
/usr/java/jdk1.7.0_79/jre/bin/java
/usr/java/jdk1.7.0_79/bin/java
/usr/bin/java
/etc/pki/ca-trust/extracted/java
/etc/pki/java
```
* find by size
```bash
[root@web_server home]# find /home -size +100M
/home/jdk-7u79-linux-i586.tar.gz
/home/jdk-7u79-linux-i586.rpm
```
* find by type (d-directory,f-regular file)
```bash
[root@web_server home]# find / -type f -name java
/usr/java/jdk1.7.0_79/jre/bin/java
/usr/java/jdk1.7.0_79/bin/java
[root@web_server home]# find / -type d -name java
/usr/java
/etc/pki/ca-trust/extracted/java
/etc/pki/java
```