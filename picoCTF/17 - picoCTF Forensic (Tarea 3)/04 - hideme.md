## Descripción
Every file gets a flag.
The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye here.
## Solución

```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/hideme]
└─$ foremost flag.png                                                                            
Processing: flag.png
|foundat=secret/UT
foundat=secret/flag.pngUT
*|   
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/hideme]
└─$ ls
flag.png  output
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/hideme]
└─$ cd output  
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/hideme/output]
└─$ ls
audit.txt  png  zip

┌──(diego㉿Maquina-deGuerra)-[~/…/forensic/hideme/output/zip]
└─$ unzip 00000077.zip 
Archive:  00000077.zip
   creating: secret/
  inflating: secret/flag.png          
┌──(diego㉿Maquina-deGuerra)-[~/…/forensic/hideme/output/zip]
└─$ ls
00000077.zip  secret 
┌──(diego㉿Maquina-deGuerra)-[~/…/forensic/hideme/output/zip]
└─$ cd secret        
┌──(diego㉿Maquina-deGuerra)-[~/…/hideme/output/zip/secret]
└─$ ls
flag.png
```

picoCTF{Hiddinng_An_imag3_within_@n_ima9e_85e04ab8}
## Notas adicionales
+ con wget descargamos el archivo
+ como no encontramos pistas usamos un zsteg para revisar datos ocultos
+ y nos topamos con una carpeta llamada secret 
+ para ver mas a fondo los datos usamos un nuevo paquete llamado foremost
+ y nos da una carpeta llamada output asi la abrimos
+ despues nos encontramos con otras dos carpetas una llamada zip y otra png
+ al abrir la carpeta zip nos encontramos un archivo.zip asi que lo descomprimimos
+ y esta nos da la carpeta secret asi que entramos a esta
+ y nos encontramos con una imagen con la bandera
## Referencias
foremost --: recupera archivos borrados o perdidos a partir de una imagen de disco o de un dispositivo