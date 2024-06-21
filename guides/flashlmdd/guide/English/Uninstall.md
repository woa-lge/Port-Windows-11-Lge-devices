 <img align="right" src="/devices/flashlmdd.png" width="350" alt="Windows 11 Running On A V50">


# Windows en el Lg V50

#### Arranca en TWRP del dispositivo

#### Desmonta todas las particiones
Ve a mount en TWRP y desmonta todas las particiones

## Pasar las herramientas necesarias:
```cmd
adb push parted /sbin
```

## Iniciar ADB shell
```cmd
adb shell
```

# Restaurar particiones
#### Darle los permisos necesarios a la herramienta
```sh
chmod +x /sbin/*
```


### Iniciar parted
```sh
parted /dev/block/sda
```

### Borrar la partición `userdata` 
>Para asegurarte de que la partición 32 es userdata puedes usar
>  `print all`
```sh
rm 32
```

### Borrar la partición `win` 
>Para asegurarte de que la partición 31 es win puedes usar
>  `print all`
```sh
rm 31
```

### Borrar la partición `esp` 
>Para asegurarte de que la partición 30 es esp puedes usar
>  `print all`
```sh
rm 30
```

### Creamos la partición de datos de Android
```sh
mkpart userdata ext4 18.4GB 126GB
```

### Salir de parted
```sh
quit
```

### Reiniciar a TWRP

- Formatea data
Ve a Wipe en TWRP y presiona Format Data, 
después escribe `yes`.

### Comprueba si android inicia
Solo reinicia el teléfono y comprueba si Android inicia

## ¡Terminado!
