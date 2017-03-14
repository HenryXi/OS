# Linux combine files into one
We use `cat` command to combine multiple files into one. Here are the examples. Let's say you have 3 files like following.

file1
```
this is file1
```
file2
```
this is file2
```
file3
```
this is file3
```
Use `cat` command combine them into one file.
```bash
cat file1 file2 file3 > combine
```
The content of combine is like following.
```
this is file1
this is file2
this is file3
```