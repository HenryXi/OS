Linux scp command examples
`scp` command can help you copy file from remote computer. Here are some examples.

**copy local file to remote**
```
# copy local file to remote 
$ scp local_file remote_username@remote_ip:remote_folder

# copy local file to remote and change the name of file
$ scp local_file remote_username@remote_ip:remote_folder/file_name

# copy local folder to remote 
$ scp -r local_folder remote_username@remote_ip:remote_folder
```

**copy remote file to local**
```
# copy remote file to local 
$ scp remote_username@remote_ip:remote_folder local_file

# copy remote file to local and change the name of file
$ scp remote_username@remote_ip:remote_folder/file_name local_file

# copy remote folder to local 
$ scp -r remote_username@remote_ip:remote_folder local_path
```
