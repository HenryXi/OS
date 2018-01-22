# Linux mint add IDEA in applications menu
After downloading and unzipping the tar.gz file of IDEA I can start it by executing `idea.sh`. But I want to add it in Linux 
mint applications menu. For Linux mint the applications menu info is in `/ usr / share / applications /`. Creating the file 
`idea.desktop` in this directory. The content is like following.
```
[Desktop Entry]
Encoding=UTF-8
Exec=/home/henry/tool/idea-IU-173.4127.27/bin/idea.sh
Icon=/home/henry/tool/idea-IU-173.4127.27/bin/idea.png
Type=Application
Terminal=false
Comment=Coding
Name=IDEA
GenericName=IDEA
StartupNotify=false
Categories=Development;IDE;Java;
```
I unzip the IDEA package in the directory `/home/henry/tool/`. You need to change the path of *.sh and *.png to yours. 
After saving this file you can find IDEA icon in your application menu and you can click it to run IDEA.

EOF  