# Files-with-trailing-space
how to create files with trailing spaces in windows
References
https://www.48bits.com/advisories/rtldospath.pdf
Windows "exploit" for adding file names with trailing space

https://learn.microsoft.com/en-us/sysinternals/downloads/winobj
device object notation windows \\?\ \\.\

"c:\Program Files" (note the quotes)
c:\PROGRA~1 (the short name notation)	8.3 filename (also called a short filename or SFN)

Example====  
(this string is a test string that should triger an alert)
echo X5O!P%@AP[4\PZX54(P^^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*>"\\?\C:\malware.exe "

Test====
echo " this is not malware" > "\\?\C:\windows\temp\notbad.exe"
echo " this IS malware SPOOKY!!" > "\\?\C:\windows\temp\notbad.exe "

DIR=====
notice only file size is different... kinda sus lets hit it with a MD5 sum....
![image](https://user-images.githubusercontent.com/92181911/235490664-03cff681-5848-4ca3-a007-bd36eb9e603a.png)

Hash====
get-filehash -algorithm md5 .\notepad.exe*
![image](https://user-images.githubusercontent.com/92181911/235490612-0621cd53-21e4-4ffe-aff1-a3b5588aa6c2.png)

how to view=====
use dir /x 
notepad notepad~1.exe 
