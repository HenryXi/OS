# Linux tar command examples
``tar`` is one of the most common commands in Linux. We usually use it to
package files. You can also compress files to save disk space during packaging.
I will show you how to use it in this tutorial. Maybe you can't remember
all parameters at one time. The more you practice the more skillful you 
will become.

-c: ``c``reate a new archive
-x：e``x``tract files from an archive
-t：lis``t`` the contents of an archive
-r：append files to the end of an archive(**why ``r`` mean append?**)
-u：only append files newer than copy in archive(``u``pdate)

You can use only **one** of these 5 parameters in a command. You can't create
a new archive meanwhile extract files from it. They are mutually exclusive.
But you can append other parameters when you want compress or extract files.

-z：filter the archive through gzip(use ``gzip`` compress the archive)
-j：filter the archive through bzip2(use ``bzip2`` compress the archive)
-Z：filter the archive through compress(use ``compress`` compress the archive)
-v：verbosely list files processed
-f: use archive file or device ARCHIVE(**must put it in the last of parameters**)

**Sample Examples**

1. Put all jpg file in all.tar. ``-c`` means create new file(all.tar), use ``-f`` specifying a file name. 
```
tar -cf all.tar *.jpg
```
2. Append all gif file in all.tar. ``-r`` means append
```
tar -rf all.tar *.gif
```
3. Update old logo.gif in all.tar with new logo.gif file 
```
tar -uf all.tar logo.gif
```
4. Show all files in all.tar
```
tar -tf all.tar
```
5. Extract all files in all.tar
```
tar -xf all.tar
```

**Compress Examples**

1. Put all jpg file in jpg.tar and show the process
```
tar -cvf jpg.tar *.jpg
```
2. Package all jpg file in jpg.tar.gz and compress it with ``gzip``
```
tar -czf jpg.tar.gz *.jpg
```
3. Package all jpg file in jpg.tar.bz2 and compress it with ``bzip2``
```
tar -cjf jpg.tar.bz2 *.jpg
```
4. Package all jpg file in jpg.tar.Z and compress it with ``compress``
```
tar -cZf jpg.tar.Z *.jpg
```

**Extract Examples**

1. Extract file.tar and show the process
```
tar -xvf file.tar
```
2. Extract file.tar.gz and show the process
```
tar -xzvf file.tar.gz
```
3. Extract file.tar.bz2 and show the process
```
tar -xjvf file.tar.bz2
```
4. Extract file.tar.Z and show the process
```
tar -xZvf file.tar.Z
```

Happy learning.