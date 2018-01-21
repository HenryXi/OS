# Linux mint make Chinese fonts clear
I have an old laptop with 4G memory and T6600 CPU. It installed Windows7 before and it runs slower and slower recently. 
I decide to install linux on it. Finally I choose Linux mint with xfce. It is not very beautiful but it's lightweight and 
use less memory. For the default Chinese fonts is not very clear. After google I use following command to make the fonts 
become clearer.
```bash
sudo ln -s /etc/fonts/conf.avail/63-wqy-zenhei-sharp.conf /etc/fonts/conf.d/
```

EOF