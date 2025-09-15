## Descripción
I accidentally wrote the flag down. Good thing I deleted it! You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/75/challenge.zip)

## Solución
primero con wget descargamos el zip luego al descomprimirlo vemos que solo tiene un archivo .txt que solo dice top secret la descripcion nos insinuo a que realizaron un commit que perdio la vandera para ver como fue la bandera ocupamos ver el historial de commits con git log al ver como el titulo de uno declara la cracion de la bandera usamos git show + la id del commit para ver el contenido y asi rescatar la bandera
```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ git log
commit 3899edb7f3110d613c72ad40083fd8feeef703d0 (HEAD, master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:58 2024 +0000

    remove sensitive info

commit 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:58 2024 +0000

    create flag
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ git show 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2
commit 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:58 2024 +0000

    create flag

diff --git a/message.txt b/message.txt
new file mode 100644
index 0000000..ed59373
--- /dev/null
+++ b/message.txt
@@ -0,0 +1 @@
+picoCTF{s@n1t1z3_9539be6b}

```
## Referencias
git log --> para ver el historial de commits
git show (id) --> es para ver el contenido que traia un commit lanzado