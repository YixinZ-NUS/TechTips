LoadLibrary failed with error 87:
>https://www.mathworks.com/matlabcentral/answers/183082-plot-loadlibrary-failed-with-error-87
I solved the problem on my own. For those having a ati graphic card, the problem is related (at least in my case) to the file "atig6pxx.dll" in windir/system32 (Our you can search for it).
I've found the solution at this link https://www.youtube.com/watch?v=D0lqBQbPVoo  and solved the problem by renaming "atig6pxx.dll" into "atig6pxx.dll.bak" (you need to change the extention of the file.)

OK, here is the full treatment:

Reboot into Safe Mode
Log on under an admin account
Open a Command Prompt (cmd.exe)
Type these commands and press Enter after each:
cd  \Windows\System32
takeown  /f  atig6pxx.dll
icacls  atig6pxx.dll  /grant  everyone:full
attrib  -r  -s  atig6pxx.dll

>https://lyyqaq.com/2021/07/31/amdbug/