# mmcblkNX-C
USB-C Hardware eMMC reader capable of reading *Nintendo Switch* raw partitions including **boot0**, **boot1** with rtsx Linux driver.  
On windows you can use https://github.com/eliboa/NxNandManager if you dont need boot0/1.  
These are the drivers I found worked on windows https://download.lenovo.com/consumer/mobiles/cr115w8.exe  


# About
I love adding USB-C to things. Figured I would do that here before I ordered them.  
[I sell these on my site.](https://shop.pbanjin.space/product/emmcc/)    
Just a hardware mod of https://github.com/ignasurba/mmcblkNX. 
It should work out of the box on modern linux, live, vm, or install.  
If using virtualbox you need to change the usb controller to usb 3.  
<img width="243" height="137" alt="image" src="https://github.com/user-attachments/assets/7f5c9435-e7ac-4db3-896f-4f72ff252dcb" />



## Usage
```
sudo dd if=/dev/mmcblk0boot0 of=boot0.bin
sudo dd if=/dev/mmcblk0boot1 of=boot1.bin
sudo dd if=/dev/mmcblk0 of=rawnand.bin
```
<img width="600" height="496" alt="image" src="https://github.com/user-attachments/assets/d33901ee-4bb2-4569-a9e7-c44ff6454309" />



## Disable read-only mode
```
sudo su
echo 0 > /sys/block/mmcblk0/force_ro
echo 0 > /sys/block/mmcblk0boot0/force_ro
echo 0 > /sys/block/mmcblk0boot1/force_ro
exit
```


# Hardware
It is fully open-source reader based on Realtek **RTS5170** card reader and designed in EasyEDA
Uses the same Molex 500913-0302 connector.

# Pictures
![PXL_20250904_040100257](https://github.com/user-attachments/assets/60c4df3e-72c6-48be-8c7b-d4f72d5f98be)
![PXL_20250904_040025149](https://github.com/user-attachments/assets/e46c7ba9-98ee-46bf-988d-be9b709e59ed)


Renders:
![3d](https://github.com/pbanj/mmcblkNX-C/blob/main/Pictures/mmcblkNX-C-Top-3D.png)  

![Top](https://github.com/pbanj/mmcblkNX-C/blob/main/Pictures/mmcblkNX-C-Top.png)  

![Bottom](https://github.com/pbanj/mmcblkNX-C/blob/main/Pictures/mmcblkNX-C-Bottom.png)  

# Disclaimer
It does not decrypt your files or enable piracy of any kind.  
It is created to make recovery possible.  
In full support of the right to repair movement.  
