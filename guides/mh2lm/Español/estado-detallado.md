# Estado Principal
- Dispositivo: LG G8X (mh2lm)
> [!IMPORTANT]
> **Esta descripción es solo para referencia. No representa ningún compromiso para desarrollar Windows en LG G8X de ninguna manera, ni significa que todas las funciones estarán disponibles o que el desarrollo se completará para siempre. No debes comprar este dispositivo con el propósito de usar Windows en él, y esperar que tendrá funciones completas al final. Las funciones disponibles hoy deben considerarse como lo máximo que puedes obtener. Debemos tener esto en cuenta al realizar la compra. No pienses que haremos que todo funcione normalmente.**

| Característica         | Notas                                                                                   | Estado         |
|------------------------|-----------------------------------------------------------------------------------------|----------------|
| ⌨️ Botones laterales   |                                                                                         | ✅            |
| ♋ Llamadas celulares  |                                                                                         | ❌            |
| ♋ Datos celulares     |                                                                                         | ❌            |
| ♋ Mensajes celulares  |                                                                                         | ❌            |
| ♋ Wifi                |                                                                                         | ✅            |
| 📦 UFS                 |                                                                                         | ✅            |
| 🔵 Bluetooth           |                                                                                         | ✅            |
| 🎆 GPU                 |                                                                                         | ✅            |
| 🔋 Batería             |                                                                                         | ✅            |
| 📌 GPS                 |                                                                                         | ✅            |
| 🪵 USB                 | Si intentas cargar el teléfono dejará de funcionar                                      | ✅            |
| 📺 HDMI / DP out       | En progreso                                                                             | ❌            |
| 🔊 Audio               |                                                                                         | ✅            |
| 🧭 Sensor              | Algunos ya están funcionando                                                            | ⚠️            |
| 🛡️ TPM                 | En progreso                                                                             | ❌            |
| 👆 Táctil              |                                                                                         | ✅            |
| 🔌 Carga               | Carga lenta únicamente                                                                  | ✅            |
| 📳 Motor de vibración  |                                                                                         | ❌            |
| 🔦 LED                 |                                                                                         | ❌            |
| 📸 Flash de cámara     |                                                                                         | ❌            |
| 🏷️ NFC                 |                                                                                         | ❌            |
| 📸 Cámara              |                                                                                         | ❌            |
| 🧬 Escáner de huellas  |                                                                                         | ❌            |

# Estado detallado

## 🔊 Audio
| Característica                | Notas                                                                                   | Estado         |
|-------------------------------|-----------------------------------------------------------------------------------------|----------------|
| 🔉 Altavoz de audio           |                                                                                         | ✅            |
| 🔉 Altavoz del auricular      |                                                                                         | ✅            |
| 🔉 AUX                        |                                                                                         | ❌            |
| 🎙️ Micrófono superior interno |                                                                                         | ✅            |
| 🎙️ Micrófono inferior interno |                                                                                         | ✅            |

## 🧭 Sensores
| Característica         | Notas                                                                                   | Estado         |
|------------------------|-----------------------------------------------------------------------------------------|----------------|
| 🧭 Acelerómetro        |                                                                                         | ✅            |
| 🧭 Giroscopio          |                                                                                         | ✅            |
| 🧭 Sensor de luz       |                                                                                         | ⚠️            |
| 🧭 Magnetómetro        |                                                                                         | ✅            |
| 🧭 Proximidad          |                                                                                         | ❌            |

## 🪵 USB
> [!NOTE]
> - Actualmente usando el modo USB Fn por defecto. Sin embargo, el usuario puede recuperar la funcionalidad del modo host con la ayuda de simples comandos reg:
> - RoleSwitchMode 1 -> USB Host
> - RoleSwitchMode 3 -> USB Fn
```batch
REM Forzar modo USB Host (idéntico a la versión anterior del controlador de este mes):
REG ADD "HKLM\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters" /v RoleSwitchMode /t REG_DWORD /d 1
```
```batch
REM Restaurar la funcionalidad de detección automática por defecto (comportamiento predeterminado):
REG ADD "HKLM\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters" /v RoleSwitchMode /t REG_DWORD /d 3
```

| Feature                         | Notes                                                                                   | Status         |
|---------------------------------|-----------------------------------------------------------------------------------------|----------------|
| 🪵 USB-Fn   (Carga & MTP)       | **[Predeterminado]** MTP no funciona todo el tiempo                                     | ✅            |
| 🪵 USB-Host (OTG)               | Algunas funciones están en progreso (dongles sin alimentación USB)                      | ⚠️            |


## 🎆 GPU 
| Feature                | Notes                                                                                   | Status         |
|------------------------|-----------------------------------------------------------------------------------------|----------------|
| 📲 Control de brillo	 |                                                                                         | ✅            |
| 🎆 Emulación X64	     |                                                                                         | ✅            |
