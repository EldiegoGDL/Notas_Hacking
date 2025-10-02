## Descripción

## Solución
primero con wget instalamos el archivo png despues ocuparemos instalar el paquete exiftool
```c
sudo apt install exiftool
```

despues usamos el comando exiftool para sacar la bandera de la imagen con la caracteristica -Artist
```c
exiftool -Artist pico_img.png
```

```
Artist                          : picoCTF{s0_m3ta_eb36bf44}

```
## Referencias
exiftool --> es un comando para leer,escribir y editar metadatos de varios formatos de imagenes
y la función -Artist es para saber el nombre del autor que creo la imagen 