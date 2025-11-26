# fix-exe-association


Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\.exe]
@="exefile"
"Content Type"="application/x-msdownload"

[HKEY_CLASSES_ROOT\exefile\shell\open\command]
@="\"%1\" %*"

[HKEY_CLASSES_ROOT\exefile\shell\runas\command]
@="\"%1\" %*"

[HKEY_CLASSES_ROOT\exefile]
@="Application"

[-HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.exe]


if Not work


assoc .exe=exefile
ftype exefile="%1" %*

.

reg add "HKCR\.exe" /ve /d "exefile" /f

reg add "HKCR\exefile\shell\open\command" /ve /d "\"%1\" %*" /f

reg delete "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.exe" /f

....


C:\Windows\System32\reg.exe add "HKCR\.exe" /ve /t REG_SZ /d "exefile" /f

C:\Windows\System32\reg.exe add "HKCR\exefile\shell\open\command" /ve /t REG_SZ /d "\"%1\" %*" /f

C:\Windows\System32\reg.exe delete "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.exe" /f



.....


reg delete "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.exe" /f

....


reg 

Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\.exe]
@="exefile"
"Content Type"="application/x-msdownload"

[HKEY_CLASSES_ROOT\exefile\shell\open\command]
@="\"%1\" %*"

[HKEY_CLASSES_ROOT\exefile\shell\runas\command]
@="\"%1\" %*"

[HKEY_CLASSES_ROOT\exefile]
@="Application"


bat


@echo off
echo ریست کردن OpenWith و کش Explorer...

:: پاک کردن OpenWith کاربر برای exe, bat, com, pif
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.exe" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.bat" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.com" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.pif" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.cmd" /f

:: پاک کردن کش آیکن‌ها
taskkill /f /im explorer.exe
del /a /q "%localappdata%\IconCache.db"
start explorer.exe

echo ریست کامل انجام شد. سیستم را ریستارت کنید.
pause


@echo off
echo ریست کردن OpenWith و کش Explorer...

:: پاک کردن OpenWith کاربر برای exe, bat, com, pif
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.exe" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.bat" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.com" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.pif" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.cmd" /f

:: پاک کردن کش آیکن‌ها
taskkill /f /im explorer.exe
del /a /q "%localappdata%\IconCache.db"
start explorer.exe

echo ریست کامل انجام شد. سیستم را ریستارت کنید.
pause

......


@echo off
echo Resetting OpenWith and Explorer icon cache...

:: Delete OpenWith settings for exe, bat, com, pif, cmd
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.exe" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.bat" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.com" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.pif" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.cmd" /f

:: Clear icon cache
taskkill /f /im explorer.exe
del /a /q "%localappdata%\IconCache.db"
start explorer.exe

echo Reset complete. Please restart your system.
pause
