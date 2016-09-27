# Use ESC to close Windows Explorer in Windows
As we all know, we can use Alt+F4 to close any windows in Window. But Alt+F4 is hard for us to press. Every time I have
to find the F4 button. I want change the way to close windows especially for Window Explorer. Recently I found 
[AutoHotkey](https://autohotkey.com/) can help me solve this problem. In this blog I will show you how to close
Windows Explorer with ESC button.
##### Download it and install
For more detail you can click [here](https://autohotkey.com/).
##### Write the script to meet your requirement
For closing Windows Explorer with ESC button the script like following works fine. Paste it into notepad and save it
as "esc_close.ahk".
```
#IfWinActive ahk_exe explorer.exe
Esc::!F4
```
##### Run this script
Double click the script will make it run in background. Now you can use ESC button to close Windows Explorer.