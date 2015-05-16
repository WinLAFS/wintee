# wintee
Automatically exported from code.google.com/p/wintee

binary for windows is here:
https://wintee.googlecode.com/files/wtee.exe
  
and
  
https://github.com/WinLAFS/wintee/releases
  
here:
  
https://github.com/WinLAFS/wintee/releases/download/v1.0.1/wtee.exe
  
wiki is downloaded as branch
  
https://github.com/WinLAFS/wintee/tree/wiki
  
  
identical aim other solution
  
see https://github.com/mpderbec/WinTee
   

example use:
  
c:\ dir >> logfile.log [standart use no cli output]
  
c:\ dir | wtee -a logfile.log [the directory will be in the logfile.log and on the screen]
  
  
c:\ dir > "c:\logs\log.txt"
  
c:\ dir | "c:\tools\wtee" "c:\logs\log.txt"
  

1) Created a folder C:\tmp\sarai lee

2) Created a file c:\tmp\sarai lee\currdate.cmd

3) The contents of the file is

@echo off date /T time /T

4) Able to log output via

"c:\tmp\sarai lee\currdate.cmd" | wtee "c:\tmp\sarai lee\long name (with spaces) for logfile.log" 




-------------------
some practical questions and solutions
-------------------
#BATCH:

> Comment by jackwrig...@gmail.com, Dec 3, 2013

Thanks for the useful utility. We've been ussing in it a batch file to catch&log the console output like this:

echo Executing scripts in SysStart?... call %~dp0\Tools\ExecuteAlphabetically?.cmd %~dp0\SysStart? | %~dp0\Tools\wtee -a %~dp0\SysStart?.log

but here's a slight problem with it, though. After ExecuteAlphabetically?.cmd has finished executing scripts from the directory SysStart? the console prompt never returns. Piping with wtee keeps the console open forever and it is not possible to write more commands in the same batch file to do something else afterwards.

\Tools\ExecuteAlphabetically?.cmd is as simple like this: ---start--- for /f %%x in ('dir /b /on %1\.cmd') do call %1\%%x ---end---

Would be nice if there was a way to signal to wtee.exe that it shoud terminate now (maybe through echoing a special sequience of escape characters to stdout or something) and do not keep waiting for input from that pipe forever, so the call returns and the file SysStart?.log and the console will be eventually closed. Thanks!

>>Comment by eloiseta...@gmail.com, Jan 2, 2014

"exit /b" in the batch file, and calling "test.bat | wtee.exe logfile.log" worked for me :) (@jackwrig)

#SPACES in filenames

> Comment by minerd...@gmail.com, May 28, 2013

Unable to run wtee in a path with spaces and uable to output to log file with spaces. When added double quotes to both wtee path and log file path the cmd window flashes and the log file never gets any output. It does work of the bat file path is in double quotes. I.e. "C:\test spaces\test.bat" 2>&1 | "C:\test spaces\wtee.exe" "C:\test spaces\output.log"

>> Comment by Tai.Aden...@gmail.com, Mar 3, 2015

Original Comment minerd...@gmail.com, May 28, 2013 Unable to run wtee in a path with spaces and unable to output to log file with spaces

1) Created a folder C:\tmp\sarai lee

2) Created a file c:\tmp\sarai lee\currdate.cmd

3) The contents of the file is

@echo off date /T time /T

4) Able to log output via

"c:\tmp\sarai lee\currdate.cmd" | wtee "c:\tmp\sarai lee\long name (with spaces) for logfile.log"

Daniel Adeniji


_______

