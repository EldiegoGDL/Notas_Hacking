## Descripción
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory. [Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz) Access checker program: `nc saturn.picoctf.net 61189`
## Solución
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/Sleuthkit_into]
└─$ mmls disk.img     
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/Sleuthkit_into]
└─$ nc saturn.picoctf.net 61189
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752 
202752 
Great work!
picoCTF{mm15_f7w!}

```

## Notas adicionales
+ primero con wget descargamos el archivo
+ luego con gunzip lo extraemos
+ despues con mmls mostramos las particiones de la imagen
+ analisarlo encontramos que el archivo esta guardado en una particion de linux
+ y en esa particion tiene el tamaño de 202752 
+ entonces procedemos a conectarnos a la conexion nc esta nos pide el tamaño de la particion de la imagen y como ya antes la habiamos buscado se la damos y obtenemos la bandera
## Referencias
