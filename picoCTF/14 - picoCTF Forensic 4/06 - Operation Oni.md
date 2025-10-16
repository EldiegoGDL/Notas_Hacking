## Descripción
Download this disk image, find the key and log into the remote machine. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download disk image](https://artifacts.picoctf.net/c/71/disk.img.gz)
- Remote machine: `ssh -i key_file -p 64947 ctf-player@saturn.picoctf.net`
## Solución
```
ctf-player@challenge:~$ cat flag.txt 
picoCTF{k3y_5l3u7h_af277f77}
ctf-player@challenge:~$ 

```

## Notas adicionales
 + primero con wget descargamos el archivo 
 + luego con gunzip lo extraemos
 + despues con mmls mostramos las particiones de la imagen
+ analisarlo encontramos que el archivo esta guardado en una particion de linux
+ despues con fls desplegamos los archivos de la particion
+ las llaves se guardan en el root asique lo inspeccionamos
+ al abrirla carpeta nos encontramos el archivo .ssh allí esta la llave ssh
+ ahora con icat sacamos los datos binarios de la llave
+ y con un cat revisamos la llave
+ despues con chmod cambiamos los permisos de la bandera para poder leerla
+ entonces nos conectamos a la conexion ssh
+ y al conseguir acceder con un cat ya podemos observar la bandera
## Referencias
