Install Windows 11 pro
  - on any PC :) 

In this repository i write some source code thet help you to install windows11pro in any PC.

Install windows 11 with pendrive and when install itt and not work, press on the keyboard:

  shift + F10

x:\Sources>diskpart

DISKPART> list disk

DISKPART> select disk 0 
    //Select the disk where you want to install the windows 11 (Ex. 0)

DISKPART> list par 
    //I make a list which included the disk partitions

DISKPART> select par 1 
    //Select the partition where you want to install the windows 11 (Ex. 1)

DISKPART> format fs=fat32 quick
    //Format the partition

DISKPART> ass letter d
    //Assign a drive letter, I will assign W using the ass letter w command.
    //If is not possibile, assign a another letter

DISKPART>  exit

x:\ d:

D:\> dir
    //az utóbbi két paranccsal ellenőrizhetek minden particiót, hogy mit is tartalmaz

D:/>DISM /Get-ImageInfo /imagefile:c:\sources\install.wim
    //lekérdezem a telepítendő windows image filjának tartalmát és kiválasztoma  megfelelő indexet (pl. 6 - Win.11Pro)

D:\>DISM /apply-image /imagefile:C:\sources\install.wim /index:6 /applydir:d:\
    //jelen esetben a C: a windows forrásparticiója a D: pedig a telepítendő célpartició

D:\>bcdboot c:
    // C: - forráspartició

D:\>bcdboot d:\Windows /s D:
    //D: - célpartició