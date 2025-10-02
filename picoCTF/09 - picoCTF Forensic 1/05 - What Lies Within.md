## Descripción
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?
## Solución
primero descargamos el archivo png con wget y luego corroboramos el contenido del archivo con file
```c
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/What_Lies_Within]
└─$ file buildings.png                
buildings.png: PNG image data, 657 x 438, 8-bit/color RGBA, non-interlaced

```

despues instalamos el paquete zsteg con gem
```c
gem install zsteg
```

despues usamos el comando zsteg mas un grep para filtrar y sacar la bandera
```c
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/What_Lies_Within]
└─$ zsteg -a buildings.png | grep pico
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"

```

## Referencias
zsteg --> sirve para detectar y extraer datos ocultos dentro de imágenes, principalmente en formatos PNG y BMP, utilizando técnicas de esteganografía como LSB o compresión zlib.