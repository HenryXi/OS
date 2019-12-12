# CentOS7 virtualBox install guest additions
In order to use share folder you have to install guest additions in VirtualBox. In this page I will show you how to install it.
Click `devices` -> `Install Guest Additions...` and wait a minute. Open terminal in CentOS7. Before installing it you need 
make sure your environment is OK.
```
yum install update
yum install kernel-headers
yum install kernel-devel
yum install gcc* 
yum install make
```
After installing above packages you can mount iso file and execute install command.
```
mkdir /mnt/cdrom
mount /dev/cdrom /mnt/cdrom
cd /mnt/cdrom
./VBoxLinuxAdditions.run
```
This will take few minutes. After installation you can config share folder between host and virtualBox.

Click `devices` -> `Shared Folders..` and config share folder path and share folder name. 

Use following command to mount shared folders in virtual system.
```
mkdir /mnt/vboxshare
mount -t vboxsf <your_share_folder_name> /mnt/vboxshare/
```

EOF