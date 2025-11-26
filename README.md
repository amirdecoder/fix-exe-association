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
