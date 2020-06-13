# Linux wget output to stdout
Use the following command to output the result of the wget command to the screen instead of saving it to a file.

```
[work@computer xxy]$ wget -O- http://10.145.180.16:19988/data/
--2020-06-13 14:29:20--  http://10.145.180.16:19988/data/
Connecting to 10.145.180.16:19988... connected.
HTTP request sent, awaiting response... 200 OK
Length: 262 [text/html]
Saving to: ‘STDOUT’

 0% [                                                                                                           ] 0           --.-K/s              <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 3.2 Final//EN"><html>
<title>Directory listing for /data/</title>
<body>
<h2>Directory listing for /data/</h2>
<hr>
<ul>
<li><a href="web.log">web.log</a>
<li><a href="web.log.18">web.log.18</a>
</ul>
<hr>
</body>
</html>
100%[==========================================================>] 262         --.-K/s   in 0s      

2020-06-13 14:29:20 (56.0 MB/s) - written to stdout [262/262]
```

EOF