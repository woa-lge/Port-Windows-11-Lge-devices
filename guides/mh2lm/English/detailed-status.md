# Main Status
- Device: LG G8X (mh2lm)
> [!IMPORTANT]
> **This description is for reference only. It does not represent any commitment to develop Windows on LG G8X in any way, nor does it mean that all functions will be available or development will be completed forever. You should not buy this device for the purpose of using Windows on it, and hope that it will have complete functions in the end. The functions available today should be considered as the most you can get.We should take this into consideration when purchasing. Don't think we will make everything normal.**

| Feature                | Notes                                                                                   | Status         |
|------------------------|-----------------------------------------------------------------------------------------|----------------|
| ⌨️ Side buttons        |                                                                                         | ✅            |
| ♋ Cellular Calls      |                                                                                         | ❌            |
| ♋ Cellular Data       |                                                                                         | ❌            |
| ♋ Cellular Texts      |                                                                                         | ❌            |
| ♋ Wifi                |                                                                                         | ✅            |
| 📦 UFS                 |                                                                                         | ✅            |
| 🔵 Bluetooth           |                                                                                         | ✅            |
| 🎆 GPU                 |                                                                                         | ✅            |
| 🔋 Battery             |                                                                                         | ✅            |
| 📌 GPS                 |                                                                                         | ✅            |
| 🪵 USB                 | If you try to charge the phone it will stop working                                     | ✅            |
| 📺 HDMI / DP out       | Work In Progress                                                                        | ❌            |
| 🔊 Audio               |                                                                                         | ✅            |
| 🧭 Sensor              |                                                                                         | ⚠️            |
| 🛡️ TPM                 | Work In Progress                                                                        | ❌            |
| 👆 Touch               |                                                                                         | ✅            |
| 🔌 Charge              | Slow charging only.                                                                     | ✅            |
| 📳 Vibration motor     |                                                                                         | ❌            |
| 🔦 LED                 |                                                                                         | ❌            |
| 📸 Camera Flash        |                                                                                         | ❌            |
| 🏷️ NFC                 |                                                                                         | ❌            |
| 📸 Camera              |                                                                                         | ❌            |
| 🧬 Fingerprint scanner |                                                                                         | ❌            |

# Detailed status

## 🔊 Audio
| Feature                | Notes                                                                                   | Status         |
|------------------------|-----------------------------------------------------------------------------------------|----------------|
| 🔉 Audio Speaker       |                                                                                         | ✅            |
| 🔉 Handset  Speaker    |                                                                                         | ✅            |
| 🔉 AUX                 |                                                                                         | ✅            |
| 🎙️ Internal Top Mic    |                                                                                         | ✅            |
| 🎙️ Internal Bottom Mic |                                                                                         | ✅            |

## 🧭 Sensors
| Feature                | Notes                                                                                   | Status         |
|------------------------|-----------------------------------------------------------------------------------------|----------------|
| 🧭 Accelerometer       |                                                                                         | ✅            |
| 🧭 Gyroscope           |                                                                                         | ✅            |
| 🧭 Light sensor        | It is detected but Windows does not change the brightness automatically                 | ⚠️            |
| 🧭 Magnetometer        |                                                                                         | ✅            |
| 🧭 Proximity           |                                                                                         | ❌            |

## 🪵 USB
> [!NOTE]
> - Currently using USB Fn mode by default. The user can however get host mode functionality back and out with the help of a simple reg commands:
> - RoleSwitchMode 1 -> USB Host
> - RoleSwitchMode 3 -> USB Fn
```batch
REM Force USB Host mode (identical to the older driver release of this month):
REG ADD "HKLM\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters" /v RoleSwitchMode /t REG_DWORD /d 1
```
```batch
REM Restore default auto detection functionality (default behavior):
REG ADD "HKLM\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters" /v RoleSwitchMode /t REG_DWORD /d 3
```

| Feature                         | Notes                                                                          | Status         |
|---------------------------------|--------------------------------------------------------------------------------|----------------|
| 🪵 USB-Fn   (Charging & MTP)    | **[Default]** MTP doesn't work all of the time                                  | ✅            |
| 🪵 USB-Host (OTG)               | Some of the features are work in progress (USB Powerless Dongles)               | ⚠️            |


## 🎆 GPU 
| Feature                | Notes                                                                                   | Status         |
|------------------------|-----------------------------------------------------------------------------------------|----------------|
| 📲 Brightness control  |                                                                                         | ✅            |
| 🎆 X64 simulation      |                                                                                         | ✅            |
