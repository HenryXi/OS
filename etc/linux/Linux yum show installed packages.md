# Linux yum show installed packages
Let's say you have installed some packages in your Linux. The following commend help you show installed packages. Use `yum`
and `grep` commends can help you find installed packages.

```bash
[root@virtual ~]# yum list installed |grep node
nodesource-release.noarch         el6-1                                installed
```

EOF