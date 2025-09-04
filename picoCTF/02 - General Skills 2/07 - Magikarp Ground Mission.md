## Descripción

Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `abcba9f7`
## Solución

lo primero que hise es conectarme al servidor ssh (` ssh ctf-player@venus.picoctf.net -p 55436 `) para luego usar un ls para ver que archivos me encontre eran instrucciones y un tal 1of3.flag al usar el comando cat pude ver que 1of3.flag era un 1/3 de la flag que buscaba al ver el contenido de las instrucciones me decia ir a la raiz del servidor y alli encontre otro tercio de la llave en 2of3.flag.txt y comence a navegar entre carpetas hasta dar con la ultima parte 3of3.flag.txt

```
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ cat instructions-to-2of3.txt
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cat 1of3.flag.txt
picoCTF{xxsh_
ctf-player@pico-chall$ cd /
pico-chall$ ls
2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
ctf-player@pico-chall$ cat 2of3.flag.txt
0ut_0f_\/\/4t3r_
```

picoCTF{xxsh_0ut_0f_\/\/4t3r_21cac893}

## Referencias

conexion ssh
comando cat para ver contenido de archivos
cd para moverse entre las carpetas