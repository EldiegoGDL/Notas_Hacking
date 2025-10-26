## Descripción
Files can always be changed in a secret way. Can you find the flag? cat.jpg
## Solución
```
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9


picoCTF{the_m3tadata_1s_modified}
```

## Notas adicionales
+ primero con wget descargamos la imagen
+ intentamos un string con grep no funciono un binwalk y tampoco
+ asi que revisamos los metadatos con exiftool
+ y al estar revisando los datos nos encontramos con una licencia encriptada 
+ asique la copiamos y desencriptamos
+ y asi conseguimos la bandera
## Referencias
