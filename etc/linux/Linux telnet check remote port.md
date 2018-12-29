# Linux telnet check remote port
We can use `telnet` to check weather the remote server port is open or not. The command is easy to use, just `telnet <IP> <port>`.
When the remote server port is open it will output like following. 
```bash
[root@virtual tmp]# telnet <remote_ip> <remote_port>
Trying <remote_ip>...
Connected to <remote_ip>.
Escape character is '^]'.
```
If the remote server port is not open the output is like this.
```bash
[root@virtual tmp]# telnet <remote_ip> <remote_port>
Trying <remote_ip>...
telnet: connect to address <remote_ip>: Connection refused
```

EOF