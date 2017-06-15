# Linux awk command examples
`awk` is more power than `grep` when you want handle the text in Linux. `awk` read the input line by line and 
split the words by space. You can also define your own separator. 

The output of `ps -ef` is like following.
```
UID        PID  PPID  C STIME TTY          TIME CMD
root         1     0  0 Jun12 ?        00:00:00 /sbin/init
root         2     0  0 Jun12 ?        00:00:00 [kthreadd]
root         3     2  0 Jun12 ?        00:00:00 [migration/0]
root         4     2  0 Jun12 ?        00:00:00 [ksoftirqd/0]
root         5     2  0 Jun12 ?        00:00:00 [stopper/0]
root         6     2  0 Jun12 ?        00:00:01 [watchdog/0]
root         7     2  0 Jun12 ?        00:00:00 [migration/1]
root         8     2  0 Jun12 ?        00:00:00 [stopper/1]
root         9     2  0 Jun12 ?        00:00:00 [ksoftirqd/1]
root        10     2  0 Jun12 ?        00:00:00 [watchdog/1]
```
If you want only get the command column. Do like this
```
$ ps -ef | awk '{print$8}'
```
$8 means the 8th column.

The content of `/etc/passwd` is here.
```
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
sync:x:5:0:sync:/sbin:/bin/sync
shutdown:x:6:0:shutdown:/sbin:/sbin/shutdown
halt:x:7:0:halt:/sbin:/sbin/halt
mail:x:8:12:mail:/var/spool/mail:/sbin/nologin
uucp:x:10:14:uucp:/var/spool/uucp:/sbin/nologin
operator:x:11:0:operator:/root:/sbin/nologin
games:x:12:100:games:/usr/games:/sbin/nologin
gopher:x:13:30:gopher:/var/gopher:/sbin/nologin
ftp:x:14:50:FTP User:/var/ftp:/sbin/nologin
nobody:x:99:99:Nobody:/:/sbin/nologin
vcsa:x:69:69:virtual console memory owner:/dev:/sbin/nologin
saslauth:x:499:76:Saslauthd user:/var/empty/saslauth:/sbin/nologin
postfix:x:89:89::/var/spool/postfix:/sbin/nologin
sshd:x:74:74:Privilege-separated SSH:/var/empty/sshd:/sbin/nologin
vboxadd:x:498:1::/var/run/vboxadd:/bin/false
mysql:x:27:27:MySQL Server:/var/lib/mysql:/bin/false
dbus:x:81:81:System message bus:/:/sbin/nologin
postgres:x:26:26:PostgreSQL Server:/var/lib/pgsql:/bin/bash
nginx:x:497:497:Nginx web server:/var/lib/nginx:/sbin/nologin
```
If you want show the username and the path of shell you can do like this.
```
$ cat /etc/passwd |awk -F ':' '{print$1 " path:" $6}'
```
":" is the separator you defined. `awk` will split this file by ":" and combine the first and 6th column.

EOF