## Descripción
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/27/fixme1.py)
## Solución
con wget descargamos el archivo .py luego con python3 lo ejecutamos al ver que este sueta un error de identacion con nano inspeccionamos el código en la propia terminal lo que paso es que el print estaba con un tabulador/espacio de mas.

```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ nano fixme1.py
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ python3 fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
```

## Referencias
nano --> es para poder modificar archivos desde la terminal
wget --> para descargar documentos
python3 -->para ejecutar el archivo.py