<img align="right" src="/devices/mh2lm.png" width="350" alt="Windows 11 Running On A LG G8x">

# Running Windows on the LG G8x

## Dualbooting Android and Windows seamlessly

### Prerequisites
- [UEFI image](https://github.com/woa-lge/msmnilePkg/releases/latest)
  
- [WOA Helper app](https://github.com/woa-lge/Port-Windows-11-Lge-devices/releases/download/dualboot/WOA-Helper.apk)

- [Instalador StA](https://github.com/woa-lge/Port-Windows-11-Lge-devices/releases/download/dualboot/StA_Installer_mh2lm.exe)

## Setting up the dualboot app
> This guide assumes you are rooted, if you aren't, please do that first

### Setup - Android
- Download and install the **WOA Helper** app, then open it and grant it root access.
- Download the **UEFI image** and place it inside the folder named `UEFI` in your internal storage.
- Open the WOA Helper app and use the **STA CREATOR** in **WOA TOOLBOX**.
> [!Important]
> If `/sdcard/Windows` is empty, your rom does not support mounting and you will have to make a boot.img backup inside the app, then copy it manually to Windows once you boot to it (for example by uploading it somewhere and then downloading it while booted into Windows). The same applies to the StA files, which are also generated in your internal storage.
>
> Do the same thing if the folder is read-only.
- Press the **QUICKBOOT TO WINDOWS** button.

### Setup - Windows
- Navigate to `C:\sta` and create a shortcut of **sta.exe** to your desktop, if one isn't already present

#### Booting to Android
- Run the new shortcut on your desktop (you can also pin it to your start menu / taskbar for ease of access)

#### Booting to Windows
- Press `QUICKBOOT TO WINDOWS` inside the app, or use the newly created toggle in your quick settings panel
  
## Finished!








