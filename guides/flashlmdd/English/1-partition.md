 <img align="right" src="/devices/flashlmdd.png" width="350" alt="Windows 11 Running On A V50">


# Windows on the LG V50

This steps are necesary to make the partitions where we are going to install Windows.

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Qfil](https://github.com/woa-lge/Port-Windows-11-Lge-devices/releases/tag/qfil)
  
- [Parted script](https://github.com/woa-lge/Port-Windows-11-Lge-devices/releases/download/parted/parted)

- [Engineering ABL](https://github.com/woa-lge/Port-Windows-11-Lge-devices/releases/download/abl/engabl_sm8150_lge.bin)
  
- [TWRP](https://github.com/woa-lge/Port-Windows-11-Lge-devices/releases/download/recoveries/twrp-installer-V50.zip)

### Notes
> [!WARNING]  
> 
> Do not run the same command twice unless specified.
>  
> Do not run all commands at once, execute them in order!
>
> YOU CAN BREAK YOUR DEVICE WITH THE COMMANDS BELOW IF YOU DO THEM WRONG!!!
>
> DO NOT REBOOT YOUR PHONE! If you think you made a mistake, ask for help in the [Telegram chat](https://t.me/lgedevices).

### Backing up partitions
> If you don't do this and mess something up, you're on your own

#### Boot TWRP on the device

#### Unmount all partitions
Go to mount on TWRP and unmount all partitions

### Preparing for partitioning
> Download the parted file and move it in the platform-tools folder, then run
```cmd
adb push parted /cache/ && adb shell "chmod 755 /cache/parted" && adb shell /cache/parted /dev/block/sda
```

#### Printing the current partition table
> Parted will print the list of partitions, **userdata** should be the last partition in the list.
```cmd
print
```

#### Removing userdata
> Replace **$** with the number of the **userdata** partition, which should be **30**
> 
> If you have a **grow** partition, remove it as well
```cmd
rm $
```

#### Recreating userdata
> Replace **17.7GB** with the former start value of **userdata** which we just deleted
>
> Replace **60GB** with the end value you want **userdata** to have
```cmd
mkpart userdata ext4 17.7GB 60GB
```

#### Creating ESP partition
> Replace **60GB** with the end value of **userdata**
>
> Replace **60.3GB** with the value you used before, adding **0.3GB** to it
```cmd
mkpart esp fat32 60GB 60.3GB
```

#### Creating Windows partition
> Replace **60.3GB** with the end value of **esp**
>
> Replace **126GB** with the end value of your disk, use `p free` to find it
```cmd
mkpart win ntfs 60.3GB 126GB
```

#### Making ESP usable
> Use `print` to see all partitions. Replace "$" with your ESP partition number, which should be 31
```cmd
set $ esp on
```

#### Exit parted
```cmd
quit
```
#### Reboot to TWRP

#### Start ADB shell again
```cmd
adb shell
```

#### Format partitions
- Format the ESP partiton as FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/by-name/esp -n ESPFLASH
```

- Format the Windows partition as NTFS
```sh
mkfs.ntfs -f /dev/block/by-name/win -n WINFLASH
```

#### Format all data
Go to the Wipe menu in your recovery and wipe all data. If this doesn't work, simply reboot your phone.

#### Check if Android still starts
> Once it is booted, it should tell you decryption was unsuccesful and it will ask you to erase all data.
- Press this button to erase all data, let the phone boot back up, then reboot back to fastboot mode.
Just reboot the phone and see if Android still boots.

## [Next step: Installing Windows](2-install.md)