## Descripción
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.
## Solución
con wget obtenemos los dos archivos y ejecutamos el archivo.py al ver que pide una contraseña. Usamos nano para ver el codigo fuente observamos que esta ves se encuentra encriptada la propia contraseña asi que la copiamos y la desincriptamos para asi obtener la contraseña volvemos a ejectar y al ya tener la contraseña accedemos a la flag

```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ nano level2.py
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ python3 level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
```
## Referencias
nano --> es para poder modificar archivos desde la terminal
wget --> para descargar documentos
python3 -->para ejecutar el archivo.py