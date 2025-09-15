## Descripción
How to automate tasks to run at intervals on linux servers? Use ssh to connect to this server:

```
Server: saturn.picoctf.net
Port: 65326
Username: picoplayer 
Password: emrdK96SGH
```

## Solución
primero usamos crontab -l para mostrar los trabajos programados.al ver que no tiene ninguno asignado abrimos con cat el archivo gloval de los trabajos programados del sistema gracias al comando cat /etc/crontab
```
picoplayer@challenge:~$ crontab -l
no crontab for picoplayer
picoplayer@challenge:~$ cat /etc/crontab
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_0bb95b71}

```

## Referencias
crontab -l --> comando para ver mis programas asignados
cat --> para abrir documentos
/etc/crontab --> es el archivo global de cron jobs del sistema