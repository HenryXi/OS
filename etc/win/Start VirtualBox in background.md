# Start VirtualBox in background
I installed VirtualBox in my computer and installed CentOS in it. When I need Linux environment I start VirtualBox and
use ssh(XShell) to connect it. It's boring to start VirtualBox by click Start menus every time. I write a bat script to
run VirtualBox in the background. It seems like this.
```
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" startvm <Your_virtual_name> --type headless
```

Now I can click this bat file and wait for CentOS start.

**How do I know if the virtual machine has started successfully?**

Add following command in bat script file. Ping this virtual machine in loop until the ping succeeds, and then connect to 
this virtual machine by a shortcut of Xshell. The contents of the entire script is like following.
```
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" startvm "linux" --type headless
:loop
timeout 2
ping -n 1 192.168.56.6 |find "TTL=" || goto :loop
D:\shortcut\virtual.lnk
```
EOF