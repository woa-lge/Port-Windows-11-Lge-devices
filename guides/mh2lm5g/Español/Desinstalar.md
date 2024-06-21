<img align="right" src="/devices/mh2lm.png" width="350" alt="Windows en el Lg G8x">

# Windows en el Lg G8x

## Desinstalando Windows

### Requisitos previos
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Qfil](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/tag/Qfil) (para restaurar particiones)
  
- [Script de Parted](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/download/Scripts/parted)
  
- [TWRP o Orange Fox](https://github.com/Icesito68/Port-Windows-11-Lge-devices/releases/tag/Recoveries)
  
- Copias de seguridad del boot

#### Restaurar copias de seguridad del boot
> Ve al modo EDL y usa Qfil para restaurar tus copias de seguridad del boot_a y boot_b

#### Arrancar TWRP en el dispositivo
> Usa el módulo Magisk vinculado arriba si aún no lo tienes instalado

#### Desmontar todas las particiones
> Ve a montar en TWRP y desmonta todas las particiones

#### Ejecutar Parted
> Pon parted en tu carpeta de herramientas de plataforma, luego ejecuta
```cmd
adb push parted /cache && chmod 755 /cache/parted && /parted /dev/block/sda
```

#### Eliminar partición de Windows
> Usa `print all` para asegurarte de que la partición 32 es de Windows
```sh
rm 32
```

#### Eliminar partición ESP
> Usa print all para asegurarte de que la partición 31 es ESP
```sh
rm 31
```

#### Redimensionar partición userdata
> Usa print all para asegurarte de que la partición 30 es userdata  
```sh
resizepart 30
126GB
```

#### Salir de Parted
```sh
quit
```

#### Formatear datos
Ve al menú de Wipe en TWRP y presiona Formatear Datos, luego escribe yes

#### Comprobar si Android arranca
Reinicia tu dispositivo y comprueba si Android arranca

## ¡Terminado!







