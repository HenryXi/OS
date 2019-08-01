# Linux sed command example
`sed` is stream editor for filtering and transforming text. I will show you how to use it to cut text into another file.
Let's say you have file(test.txt) like following.
```
cc89e38d6c3eb79fbf2e945340f06c3d
32f442c6370bcdca5af137f949925d79
5474ac325ac5c4a6789eb15b54b9aa6f
dea94101753204996968b2b498d8b631
951d63b8b571c45a0efc29b98144bd92
b28e7bd8360eafe60c1aa7cce57d3b45
ef1bf8b99758bd91c11f3baed0276665
21d1d794b11ba2ba1a72d34aea495d43
6c72d8bf1b3c18f8ebd5a3a22d808b96
1dd05cc115054c9966579c6cba121771
b3e2c38ab0c63ac4b69c08cb80d49180
8a1a11d1e906bb56e74f0c18bfe67443
689947f3483171e1e7b273ab8e8ae06d
2c7e24b1c80c724cf80d6afafda3fad7
```
If you want to cut the sixth to tenth lines into another file. You can use following command.
```bash
$ sed -n '6,10p' test.txt > part.txt
$ cat part.txt 
b28e7bd8360eafe60c1aa7cce57d3b45
ef1bf8b99758bd91c11f3baed0276665
21d1d794b11ba2ba1a72d34aea495d43
6c72d8bf1b3c18f8ebd5a3a22d808b96
1dd05cc115054c9966579c6cba121771
```

EOF
