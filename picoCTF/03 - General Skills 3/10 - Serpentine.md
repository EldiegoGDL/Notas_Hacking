## Descripción
Find the flag in the Python script! [Download Python script](https://artifacts.picoctf.net/c/35/serpentine.py)
## Solución
cargamos el script con wget para despues ejecutarlo con python3,al ver que nos topamos con un menu con la opcion de darnos la bandera pero como esta dice que olvido poner la funcion que lo imprime,usamos el comando nano para acceder y modificar el script,se observo que este cuenta con la funcion que nos imprime la flag asique la ponemos al inicio de la ejecucion del codigo para que directamente nos de la flag sin necesidad de interactuar con el menu.

```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ python3 serpentine.py
/home/el-diego/Documentos/seguridad en redes/serpentine.py:38: SyntaxWarning: invalid escape sequence '\ '
  '''
picoCTF{7h3_r04d_l355_7r4v3l3d_ae0b80bd}

    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~

Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b

Oops! I must have misplaced the print_flag function! Check my source code!

```
## Referencias
wget --> para cargar documentos
python3 --> para ejecutar archivos.py
nano --> para poder editar archivos
principios de referencia ( llamada ) de funciones