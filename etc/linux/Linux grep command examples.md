# Linux grep command examples
``grep`` command can help you search words (actually a regular expression) in file. You can also use it with other command
to print the word you want find. ``grep`` is short for "globally search a regular expression and print". There are two things
in ``grep`` command, search and print. All the parameters in ``grep`` centered on them. I will show you the common use of 
`grep``.

**search in file**

```bash
# search "hello" in access.log file
grep 'hello' access.log 
```
if you want highlight "hello" you can do like this
```bash
# hightlight the word you search
grep 'hello' access.log --color
```
if you want see the around lines of matching line you can use ``-A``(after-context),``-B``(before-context),``-C``(both 
after and before context).
```bash
#show the 3 lines after matching lines
grep 'hello' access.log -A 3

#show the 3 line before matching lines
grep 'hello' access.log -B 3

#show both after and before matching lines
grep 'hello' access.log -C 3
```
if you want ignore the case just add ``-i``
```bash
#search 'hello','Hello','HELLO'...
grep 'hello' access.log -i
```


**search with other command**

use ``grep`` with other command can help you find matching lines
```bash
#find the processes of java
ps -ef | grep 'java'

#find the log file of 2016-04-01
ll | grep '2016-04-01'

#show the log line only contain 'userid:1188'
tail -f info.log | grep 'userid:1188'
```


**make grep faster**

The examples above only show how to search a word in a file. You can replace 'word' with regular expression. If you just
search a word you can use ``-F`` or use ``fgrep`` directly which is faster than ``grep``. 
```bash
# faster than grep
grep 'hello' access.log -F 
fgrep 'hello' access.log
```
