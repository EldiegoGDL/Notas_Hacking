## Descripcion:
* The flag is somewhere on this web application not necessarily on the website. Find it.
Additional details will be available after launching your challenge instance.

## Solucion

nos encontramos una pagina completa y al estar revisando codigo fuente y archivos de este no encontramos nada asi que revisamos el documento robots.txt
```
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```
al conocer esas carpetas y tener que usar /cgi -bin/ para deshabilitarlas las revisamos una por una 
al ver que ninguna funciona revisamos si las carpetas estan encriptadas y si lo estan las vamos revisando en la url.
```
anMvbXlmaWxlLnR4dA

a base64 quedo

js/myfile.txt

```
por ello nos dirigimos a la carpeta js/myfile.txt
```
picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}
```
y asi obtuvimos la bandera
## Referencias: