## Descripción
Someone's commits seems to be preventing the program from working. Who is it? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/73/challenge.zip)
## Solución
primero con wget descargamos el zip luego al descomprimirlo vemos que solo tiene un archivo .py al ejecutarlo solo muestra un mal print pero al ver el historial de commits son varios y para revisar el historial de cambios del archivo en todos los commits usamos una regla en el comando quedando git log -p (nombre del archivo) y al leer las descripciones encontramos la bandera.

```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ cat message.py
print("Hello, World!"
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ git log -p message.py
commit fadeca9476b6713ec8cdda633aca9e9aebffc698
Author: picoCTF{@sk_th3_1nt3rn_e9957ce1} <ops@picoctf.com>
Date:   Sat Mar 9 21:09:11 2024 +0000

    optimize file size of prod code

diff --git a/message.py b/message.py
index 7df869a..326544a 100644
--- a/message.py
+++ b/message.py
@@ -1 +1 @@
-print("Hello, World!")
+print("Hello, World!"

commit 2dd46769e2d65656bb14aed0ff5d3237daaa7d9d
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:11 2024 +0000

    create top secret project

diff --git a/message.py b/message.py
new file mode 100644
index 0000000..7df869a
--- /dev/null
+++ b/message.py
@@ -0,0 +1 @@
+print("Hello, World!")

```

## Referencias
unzip --> para desempaquetar archivos .zip
cat -->para ver el contenido de archivos
git log -p (archivo) -->comando para ver los cambios de un archivo en comits que lo han modificado.