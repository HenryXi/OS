# Linux crontab example
The `crontab` command can be used to create timed tasks. Here are some simple examples.

```
*         *　　 *　　   *　　   *　　<command>
minute  hour　 day　 month　 week　 command or bash
```

Next I will show you how to configure a timed execution script. Let's say you have script like following.
```
echo "hi"
```

Use `crontab -e` to edit the configuration like following.
```bash
*/1 * * * * /root/hello
```

Use `crontab -l` to list all configurations.
```bash
[root@localhost ]# crontab -l
*/1 * * * * /root/hello >> /tmp/hello
```

Use the following command to monitor the output of the log.
```bash
tailf -f /tmp/hello
```

EOF
