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
