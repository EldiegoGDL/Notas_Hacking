## Descripción
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/237/atbash.jpg).
## Solución
```
sudo apt install steghide



┌──(diego㉿Maquina-deGuerra)-[~/Documentos/Crypto/HideToSee]
└─$ steghide --extract -sf atbash.jpg
Anotar salvoconducto: 
anot� los datos extra�dos e/"encrypted.txt".

┌──(diego㉿Maquina-deGuerra)-[~/Documentos/Crypto/HideToSee]
└─$ ls
atbash.jpg  encrypted.txt                                          
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/Crypto/HideToSee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_05y2z65z}

```
## Notas adicionales
+ con wget descargamos el archivo que nos proporcionaron
+ para despues con file ver que tipo de archivo es 
+ al ver que es un jpg
+ instalamos un nuevo paquete steghide
+ para luego usar el comando steghide con la funcion de extraccion para sacar los archivos que tenga el jpg
+ con el archivo .txt que nos dieron le hacemos un cat
+ al ver que es un encriptado Atbash lo desincriptamos y conseguimos la bandera
## Referencias

steghide es una herramienta de esteganofia para ocultar archivos o mensajes dentro de otros archivos