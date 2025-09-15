
## Descripción
What was I last working on? I remember writing a note to help me remember... You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/68/challenge.zip)
## Solución
volvemos a usar wget para descargar el archivo y procedemos a desempaquetarlo al acceder al zip vemos otro mensaque que nos indica revisar el historial de commits y al usar git log logramos ver la bandera
```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ ls
challenge.zip  drop-in
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ cd drop-in/
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ ls
message.txt
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ cat message.txt
This is what I was working on, but I'd need to look at my commit history to know why...el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ 
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ git log
commit 705ff639b7846418603a3272ab54536e01e3dc43 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:36 2024 +0000

    picoCTF{t1m3m@ch1n3_b476ca06}

```

## Referencias
wget --> descargar archivos por url
git log --> para visualizar el historial de commits hechos