## Descripción

Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/504/big-zip-files.zip)
## Solución

primero con el wget cargamos el zip al sistema con unzip lo desempaquetamos en una carpeta para poder acceder a su contenido al ver que se trataba de multiples archivos usamos el filtro grep -r  "pico" para poder encontrar la bandera entre todas las carpetas y archivos

```
DiegoGDL-picoctf@webshell:~/big-zip-files$ grep -r pico
folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
```
## Referencias

grep -r : es un comando que busca la coincidencia de una palabra en todos los archivos y subcarpetas en el directorio actual