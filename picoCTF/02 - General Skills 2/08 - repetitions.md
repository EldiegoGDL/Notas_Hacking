## Descripción
Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/475/enc_flag).
## Solución
usamos el comando cat para ver el contenido del archivo que nos proporcionaron al ver que se trata de un cifrado en base64, usamos el comando base64 -d para revertir el cifrado al ver que resulta en otro cifrado base64 concatenamos otro desifrado " |  base64 -d"  hasta dar con la flag.

![[Pasted image 20250904095050.png]]

## Referencias

comando base64 -d -->se usa para revertir encriptaciones en base64
comando cat --> se usa para ver el contenido de un archivo
