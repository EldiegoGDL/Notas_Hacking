## Descripción
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/2e739f9e0dc9f4c1556ea6b033c3ec8e/Forensics%20is%20fun.pptm)
## Solución
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/MacroHard_WeakEdge]
└─$ cat ppt/slideMasters/hidden 
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q   
```

```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/MacroHard_WeakEdge]
└─$ cat ppt/slideMasters/hidden | tr -d ' '
ZmxhZzogcGljb0NURntEMWRfdV9rbjB3X3BwdHNfcl96MXA1fQ 
```

```
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}
```
## Notas adicionales
+ con wget descargamos el archivo del reto
+ al ser un archivo de powerpoint nos damos cuenta que esta desactivada la Macros
+ descomprimimos el archivo para un analisis mas profundo
+ al encontrar un archivo llamado hidden lo inspeccionamos con un cat
+ con este texto hacemos un tr para eliminar los espacios
+ como este es un texto encriptado nos damos cuenta que se trata de una encriptacion base64
+ usamos un desincriptador de base64 y conseguimos la bandera
## Referencias
Disable Macros = es una seguridad del estado por defecto de los pptm para que al abrirse no roben datos