<img align="right" src="/devices/flashlmdd.png" width="350" alt="Windows 11 Running On To LG v50">


# Windows on the Lg V50

# Install Windows

### Prerequisites
- [Windows on ARM image](https://worproject.com/esd)
  
- [Drivers](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/tag/Drivers)

- [Mass storage image](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Files/msc.img)


# Previous

- Make a backup of the Boot_a and Boot_b partitions with Qfil

- With Qfil, flash "LGG8XMassStorageBoot.img" in boot.
  
- Then exit EDL, so your PC will recognize the V50 as a disk

## Assign letters to disks
  

#### Start the diskpart

> Once the V50 is detected as a disk

```cmd
diskpart
```


### Assign letter `x` to Windows volume

#### Select the phone's Windows volume
> use `list volume` to find it, usually it's the one before the last one

```diskpart
select volume <number>
```

#### Assign the letter x
```diskpart
assign letter=x
```

### Assign `y` to esp volume

#### Select phone esp volume
> use `list volume` to find it, usually it's the last one

```diskpart
select volume <number>
```

#### Assign letter y

```diskpart
assign letter=y
```

### Exit Windows diskpart:
```diskpart
exit
```

## Install

> replace `<path/to/Install.wim>` with the path of the install.wim file

> `install.wim` is in the sources folder of the ISO,
> you can get it after mounting or extracting the ISO

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```


# Install the Drivers

> open a cmd as Administrator

> replace `<flashlmddriversfolder>` with the location of the drivers folder

```cmd
driverupdater.exe -d <flashlmdddriversfolder>\definitions\Desktop\ARM64\Internal\flashlmdd.txt -r <flashlmdddriversfolder> -p X:
```

  

# Create the Windows bootloader files

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

  
  

# Allow unsigned drivers

> if you don't do this you will get a BSOD

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```


# [We are almost done, let's put the dual boot](3-Dual-Boot.md )
