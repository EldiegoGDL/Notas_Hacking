## Descripción
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: [dds1-alpine.flag.img.gz](https://mercury.picoctf.net/static/f63e4eba644c99e92324b65cbd875db6/dds1-alpine.flag.img.gz)
## Solución
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/Disk_disk_sleuth!]
└─$ srch_strings dds1-alpine.flag.img | grep pico 
ffffffff81399ccf t pirq_pico_get
ffffffff81399cee t pirq_pico_set
ffffffff820adb46 t pico_router_probe
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_ad5c96c0}
```

## Notas adicionales
+ primero con wget descargamos el archivo
+ luego con gunzip lo extraemos
+ usamos srch_strings combinado con un grep para que bisque las coincidencias y nos de la bandera
## Referencias
gunzip --> comando para extraer datos de archivos .gz
srch_strings --> es el texto o patron que se busca desntro de otro contenido