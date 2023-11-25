# OSED
## Narly
* Put narly.dll in C:\Program Files\Windows Kits\10\Debuggers\x86\winext\
![Alt text](Images/image-2.png)

## WinDBG GUI
* Load Workspace from File
![Alt text](Images/image.png)
![Alt text](Images/image-1.png)

## ROP++
* Run rp-win.exe
```
rp-win.exe --file narly.dll -r 5 --bad-bytes 00,01 > rop.txt
```
![Alt text](Images/image-3.png)
