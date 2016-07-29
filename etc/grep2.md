# Search string in linux directory
`grep` command can help you search specific string in file. Learn basic use of it click [here](http://www.henryxi.com/linux-grep-command-examples). 
`grep` is very powerful. It can help us to search specific string in a Linux directory. For example, we have two files
in tmp directory. 
```bash
[root@localhost tmp]# cat txt1
This is text 1
[root@localhost tmp]# cat txt2
This is text 2
```
We use `grep` to search "text" in /tmp directory.
```bash
[root@localhost tmp]# grep text ./ -rn
./txt2:1:This is text 2
./txt1:1:This is text 1
```
-r means read all files under each directory, recursively.

-n means show the match line number.