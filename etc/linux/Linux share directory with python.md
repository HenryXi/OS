# Linux share directory with python
Sometimes we need copy file from server to local. There are several ways to do that. We can use `scp`, `sz` commands to 
transfer files. `scp` command need us to input local IP, username and password. `sz` command need us to install `lrzsz`.
Today I found another way to do this. 

Use `python -m SimpleHTTPServer <port>`. `python` command is installed for most Linux OS. After executing this command.
current directory will shared by this port. You can access these files by browser. Just input `remote server IP:port` in
the address bar.


EOF 