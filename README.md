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

## Mona
1. Install python-2.7.17.msi
2. Install vcredist_x86.exe
3. Put pykd.pyd in C:\Program Files\Windows Kits\10\Debuggers\x86\winext\
4. Put windbglib.py in C:\Program Files\Windows Kits\10\Debuggers\x86\
5. Put mona.py in C:\Program Files\Windows Kits\10\Debuggers\x86\
6. Open cmd.exe with Administrator Privilege
```
cd "C:\Program Files\Common Files\Microsoft Shared\VC\"
regsvr32 /s msdia90.dll
```
7. Set Folder Permission
![Alt text](Images/image-5.png)
8. Start Mona
```
.load pykd.pyd
!py mona
!py mona.py rop -m *.dll -cp nonull
!py mona.py rop -m *.dll -cp -cpb '\x00\x3b'
```
![Alt text](Images/image-4.png)

## filter-ropfile.py
```
python3 filter-ropfile.py rop.txt                                              
```
![Alt text](Images/image-6.png)
![Alt text](Images/image-7.png)