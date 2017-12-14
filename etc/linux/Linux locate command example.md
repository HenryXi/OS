# Linux locate command example
`locate` command can help you to find the location of file in Linux. Before using `locate` you need use `updatedb` command 
to update the database. `locate` command searchs file name in database , `find` command searchs file in real time. `locate` 
is quicker than `find`. 
```bash
[root@virtual tmp]# updatedb
[root@virtual tmp]# locate bashrc
/etc/bashrc
/etc/skel/.bashrc
/root/.bashrc
[root@virtual tmp]#
```
EOF