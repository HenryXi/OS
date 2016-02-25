# The easiest way to transfer files between Windows and Linux
There are many ways to transfer files between Windows and Linux, but they are not satisfactory.

* FTP 

you have to install FTP server and start the service. Keep the service on or when you need transfer you have to 
 start service first.

* SCP 

you have to type long command in terminal. 
I hate long command. I hate input username and password(especially strong password).

* Putty

if you use UI you have to open a new window and input username and password again.
if you use commandline it's same with SCP(long command).

Is there a easier way to transfer between windows and Linux?  
YES!  
Install lrzsz 
```
    sudo yum install lrzsz
```
if you want download file from Linux to windows use "sz"
```
    sz <file_full_name>
```
if you want upload file from windows to Linux use "rz", then choose the file click OK button.



