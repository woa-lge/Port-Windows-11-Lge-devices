 <img align="right" src="/devices/flashlmdd.png" width="350" alt="Windows 11 Running On A V50">


# Windows on the Lg V50

This steps are necesary to make the partitions where we are going to install Windows.

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Qfil](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/tag/Qfil)
  
- [Parted script](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Files/parted)

- [Engineering ABL](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Files/engabl_ab.bin)
  
- [TWRP](https://xdaforums.com/attachments/twrp-installer-v3-3-1-v50_ab-zip.5070997/)

### Notes
> [!WARNING]  
> 
> Do not run the same command twice unless specified.
>  
> Do not run all commands at once, execute them in order!
>
> YOU CAN BREAK YOUR DEVICE WITH THE COMMANDS BELOW IF YOU DO THEM WRONG!!!
>
> DO NOT REBOOT YOUR PHONE! If you think you made a mistake, ask for help in the [Telegram chat](https://t.me/winong8x).

### Backing up partitions
> If you don't do this and mess something up, you're on your own

#### Boot TWRP on the device

#### Unmount all partitions
Go to mount on TWRP and unmount all partitions

## Preparing for partitioning
```cmd
adb push parted /sbin/ && adb shell "chmod 755 /sbin/parted" && adb shell /sbin/parted /dev/block/sda
```

### Delete the `grow` partition
>To make sure that partition 31 is grow you can use
>  `print all`
```sh
rm 31
```

### Delete the `userdata` partition 
>To make sure that partition 30 is userdata you can use
>  `print all`
```sh
rm 30
```

### Create partitions
> If you get any warning message telling you to ignore or cancel, just type i and enter

#### For all models:

- Create the ESP partition (stores Windows bootloader data and EFI files)
```sh
mkpart esp fat32 18.4GB 19GB
```

- Create the main partition where Windows will be installed to
```sh
mkpart win ntfs 19GB 75.5GB
```

- Create the Android data partition
```sh
mkpart userdata ext4 75.5GB 126GB
```


### Make ESP partiton bootable so the EFI image can detect it
```sh
set 30 esp on
```

### Exit parted
```sh
quit
```

### Reboot to TWRP

### Start ADB shell again
```cmd
adb shell
```

### Format partitions
- Format the ESP partiton as FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/by-name/esp
```

- Format the Windows partition as NTFS
```sh
mkfs.ntfs -f /dev/block/by-name/win
```

- Format Android data
Go to Wipe menu and press Format Data, then type `yes`.

### Check if Android still starts
Just reboot the phone and see if Android still boots.


## [Next step: Installing Windows](2-Instalation.md)
