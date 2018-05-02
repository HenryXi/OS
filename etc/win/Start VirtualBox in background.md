# Start VirtualBox in background
I installed VirtualBox in my computer and installed CentOS in it. When I need Linux environment I start VirtualBox and
use ssh(XShell) to connect it. It's boring to start VirtualBox by click Start menus every time. I write a bat script to
run VirtualBox in background. It seems like this.
```
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" startvm <Your_virtual_name> --type headless
```

Now I can click this bat file and wait for CentOS start.

EOF