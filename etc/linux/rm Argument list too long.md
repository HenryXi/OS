# rm Argument list too long
When I use `rm *.log -rf` to delete the files I got the following error message.
```
bash: /bin/rm: Argument list too long
```
This message means that there are too many files to delete. I use `find` commands to delete these files instead.

```bash
find /home/work/log/ -name *.log -delete
```

You can also use `xargs` to delete files. Following command will delete all files in current directory directly.
```bash
ls | xargs rm
```

EOF