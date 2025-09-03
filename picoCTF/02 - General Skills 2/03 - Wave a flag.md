## Descripción

Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm) has extraordinarily helpful information...
## Solución

cargamos el archivo a la terminal con:
wget + url del archivo

le damos permisos para poderlo ejecutar con chmod - x

despues el programa nos pedira que usemos -h para pedir ayuda al archivo

```
DiegoGDL-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm
--2025-09-03 16:46:45--  https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                          100%[==============================================>]  10.68K  --.-KB/s    in 0s      

2025-09-03 16:46:45 (373 MB/s) - 'warm' saved [10936/10936]

DiegoGDL-picoctf@webshell:~$ chmod +x warm
DiegoGDL-picoctf@webshell:~$ ls
README.txt  strings  warm
DiegoGDL-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
DiegoGDL-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_d6969390}
```

## Referencias

-h :es un comando que siempre nos ayuda
chmod -x :espara der permisos de ejecucion

asi se ejecuta un programa en terminal : ./[nombre del archivo]