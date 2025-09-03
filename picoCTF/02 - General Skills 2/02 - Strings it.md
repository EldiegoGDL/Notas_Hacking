## Descripción

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?
## Solución
cargamos el archivo a la terminal con:
wget + url del archivo

despues usamos el comando strings para buscar secuencias de caracteres en el archivo y usamos un grep para filtrar la flag.

```
DiegoGDL-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_7f766a23}
```

ademas se requieren permisos para ejecutar el archivo
## Referencias

wget [url] para cargar archivos con solo la url

comando strings [nombre del archivo] | grep [filtro]