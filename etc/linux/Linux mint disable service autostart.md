# Linux mint disable service autostart
For linux mint there are many service scripts in the directory `/etc/init.d`. Most of them will be executed when user login. 
Linux uses different directory (such as `/etc/rc?.d/`) to mark which service and when to run. If you don't want one service 
auto start you need to remove the link from the directory or to use `update-rc.d` command like following. 

```
sudo update-rc.d tomcat disable
```
Use `man update-rc.d` to get more details about linux service.

EOF