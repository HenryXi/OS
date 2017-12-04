# Linux yum install rpm file locally
As we all known `yum install <package_name>` can help you install the program easily. If the program doesn't exist in yum
list you can download them and install locally.

```bash
wget <package_download_url>
rpm -ivh <package_path>
```

EOF