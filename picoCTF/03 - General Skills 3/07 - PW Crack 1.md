## Descripción
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/11/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/11/level1.flag.txt.enc) in the same directory too.
## Solución
con wget obtenemos los dos archivos y ejecutamos el archivo.py al ver que pide una contraseña. Usamos nano para ver el codigo fuente y asi obtener la contraseña volvemos a ejectar y al ya tener la contraseña accedemos a la flag

```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ nano level1.py
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ python3 level1.py
Please enter correct password for flag: 1e1a
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_fa343060}

```

## Referencias
nano --> es para poder modificar archivos desde la terminal
wget --> para descargar documentos
python3 -->para ejecutar el archivo.py