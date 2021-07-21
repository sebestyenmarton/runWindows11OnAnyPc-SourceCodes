Install Windows 11 pro
  - on any PC :) 

In this repository i write some source code thet help you to install windows11pro in any PC.

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

D:\>DISM /apply-image /imagefile:C:\sources\install.wim /index:6 /applydir:d:\

D:\>bcdboot c:

D:\>bcdboot d:\Windows /s D: