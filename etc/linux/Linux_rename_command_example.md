# Linux rename command example
As we know `mv` command can help me to rename one file. `rename` is another command to rename file and files. `rename` command is very useful when you want to rename multiple files. For example you have three files like following.
```
$ ll
total 0
-rw-r--r--. 1 root root 0 Apr 20 09:40 test1.txt
-rw-r--r--. 1 root root 0 Apr 20 09:40 test2.txt
-rw-r--r--. 1 root root 0 Apr 20 09:40 test3.txt
```
If you want rename them to 'new_test1.txt', 'new_test2.txt' and 'new_test3.txt'. You can use `mv` command rename them one by one. I recommand you to use  `rename` command to rename them at once.
```
$ rename test new_test test?.txt
$ ll
total 0
-rw-r--r--. 1 root root 0 Apr 20 09:40 new_test1.txt
-rw-r--r--. 1 root root 0 Apr 20 09:40 new_test2.txt
-rw-r--r--. 1 root root 0 Apr 20 09:40 new_test3.txt
```
EOF
