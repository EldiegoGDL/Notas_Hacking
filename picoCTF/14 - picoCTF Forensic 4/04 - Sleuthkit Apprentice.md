## Descripción
Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/136/disk.flag.img.gz)
## Solución
mmls
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/Sleuthkit_Apprentice]
└─$ mmls disk.flag.img       
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)

```
fsstat
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/Sleuthkit_Apprentice]
└─$ fsstat -o 2048 disk.flag.img          
FILE SYSTEM INFORMATION
--------------------------------------------
File System Type: Ext4
Volume Name: 
Volume ID: 8e023955b4e7dab7e04b7643076ccf0f


```
fls | grep
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/Sleuthkit_Apprentice]
└─$ fls -i raw -f ext4 -o 360448 -r disk.flag.img | grep flag
++ r/r * 2082(realloc): flag.txt
++ r/r 2371:    flag.uni.txt

```
icat
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/Sleuthkit_Apprentice]
└─$ icat -i raw -f ext4 -o 360448 -r disk.flag.img 2371
picoCTF{by73_5urf3r_3497ae6b}

```
## Notas adicionales
+ primero con wget descargamos el archivo
+ luego con gunzip lo extraemos
+ despues con mmls mostramos las particiones de la imagen
+ analisarlo encontramos que el archivo esta guardado en una particion de linux
+ y con fsstat revisamos el tipo de sistema del archivo
+ despues con fls desplegamos los archivos de la particion
+ al no encontrar muchas cosas le agregamos un grep para encontrar la bandera si esque esta
+ al encontrar dos archivos con referencia a la bandera usamos un icat para extraer los datos binarios de cada uno de estos hasta dar con la bandera
## Referencias
mmls --> sirve para mostrar la tabla de particiones de un dispositivo imagen de disco
fsstat --> sirve para mostrar informacion detallada sobre el sistema de archivos en una particion
fls --> es para listar los archivos y directorios de una particion(con -i revisamos el tipo de imagen)(con -f revisamos el tipo de archivo del sistema)(con-r despliega los directorios recursivamente)
icat -->extrae el contenido binario o completo de un archivo especifico