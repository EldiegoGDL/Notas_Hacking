## Descripción
This [garden](https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg) contains more than it seems.
## Solución
primero con un wget descargamos la imagen que nos da el reto.
despues con el comando strings mas un grep podemos filtrar los datos encriptados de la imagen para encontrar la bandera 

```c
──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/gloruofhegarden]
└─$ strings garden.jpg | grep pico
Here is a flag "picoCTF{more_than_m33ts_the_3y3eBdBd2cc}"

```
## Referencias