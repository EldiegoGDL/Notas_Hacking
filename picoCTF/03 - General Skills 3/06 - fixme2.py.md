## Descripción
Fix the syntax error in the Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/6/fixme2.py)
## Solución
con wget descargamos el archivo .py luego con python3 lo ejecutamos al ver que este sueta un error de identacion con nano inspeccionamos el código en la propia terminal lo que paso es que el comparador "=" estaba mal ya que en python los comparadores ocupandoble igual ==
```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ nano fixme2.py
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ python3 fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}
```
## Referencias
nano --> es para poder modificar archivos desde la terminal
wget --> para descargar documentos
python3 -->para ejecutar el archivo.py