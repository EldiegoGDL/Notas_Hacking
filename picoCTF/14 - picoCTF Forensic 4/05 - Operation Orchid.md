## Descripción
Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/214/disk.flag.img.gz)
## Solución
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/Operation_Orchid]
└─$ openssl aes256 -d -salt -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40B784ED107F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/Operation_Orchid]
└─$ cat flag.txt                                                                        
picoCTF{h4un71ng_p457_1d02081e}   
```

## Notas adicionales
 + primero con wget descargamos el archivo
 + luego con gunzip lo extraemos 
 + despues con mmls mostramos las particiones de la imagen
 + despues con fls desplegamos los archivos de la particion
 + y buscamos informacion en la carpeta root
 + en esta encontramos dos archivos con el nombre flag asi que los revisamos con icat
 + al ver que esta es ilegible usamos un grep a la imagen
 + y con otro icat scamos el archivo flag.txt.enc
 + y nos vamos a /tmp para pegar el comando openssl que vimos al hacer el grep a la imagen
 + y le hacemos un cat al archivo flag.txt y conseguimos la bandera
## Referencias
