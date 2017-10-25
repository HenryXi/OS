# Linux show folder(directory) size
Use `du` command to show the size of folder. Before testing this command we will create a directory and a file.
```bash
[root@virtual ~]# mkdir my_directory
[root@virtual ~]# cd my_directory/
[root@virtual my_directory]# touch my_file.txt
[root@virtual my_directory]# echo 'the content of file' > my_file.txt 
[root@virtual my_directory]# cd ..
[root@virtual ~]# ll
total 16
drwxr-xr-x. 4 root root 4096 Oct 25 11:28 code
drwxr-xr-x. 4 root root 4096 Feb  8  2017 data
drwxr-xr-x. 2 root root 4096 Oct 25 20:23 my_directory
drwxr-xr-x. 5 root root 4096 Oct 25 11:51 tool
```
Use `du` to show the size of directory.The useful parameters of `du` are here.
```
-h, --human-readable
   print sizes in human readable format (e.g., 1K 234M 2G)
-s, --summarize
   display only a total for each argument
-c, --total
   produce a grand total
```
The total example is here.
```bash
[root@virtual ~]# du -sh my_directory/
8.0K	my_directory/
[root@virtual ~]# du -sh *
13M	code
284M	data
8.0K	my_directory
60M	tool
[root@virtual ~]# du -shc *
13M	code
284M	data
8.0K	my_directory
60M	tool
356M	total
```
EOF