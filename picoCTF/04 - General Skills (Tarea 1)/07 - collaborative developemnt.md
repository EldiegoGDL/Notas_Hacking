## Descripción
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/69/challenge.zip)
## Solución
para este reto igual con wget descargamos el zip y lo descomprimimos al ver que este cuenta con 3 ramas de desarrolladores procedemos a ver el historial de modificaciones del mismo archivo con cada rama hasta poder juntar las 3 partes de la bandera.

```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ git branch -a
  feature/part-1
  feature/part-2
  feature/part-3
* main
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ git checkout feature/part-1
Cambiado a rama 'feature/part-1'
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ git log
commit ad37f59bfdcb1e8052bf7e12e1d89a2adb315cf9 (HEAD -> feature/part-1)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    add part 1

commit eb4de2a9826332633c62e44a1a130d9b1a88171a (main)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    init flag printer
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ git log -p flag.py
commit ad37f59bfdcb1e8052bf7e12e1d89a2adb315cf9 (HEAD -> feature/part-1)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    add part 1

diff --git a/flag.py b/flag.py
index 77d6cec..6e17fb3 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,2 @@
 print("Printing the flag...")
+print("picoCTF{t3@mw0rk_", end='')
\ No newline at end of file

commit eb4de2a9826332633c62e44a1a130d9b1a88171a (main)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    init flag printer

diff --git a/flag.py b/flag.py
new file mode 100644
index 0000000..77d6cec
--- /dev/null
+++ b/flag.py
@@ -0,0 +1 @@
+print("Printing the flag...")
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ git checkout feature/part-2
Cambiado a rama 'feature/part-2'
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ git log -p flag.py
commit 9792a89fa347abc711f84b7208db18d164d45aca (HEAD -> feature/part-2)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    add part 2

diff --git a/flag.py b/flag.py
index 77d6cec..7ab4e25 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,3 @@
 print("Printing the flag...")
+
+print("m@k3s_th3_dr3@m_", end='')
\ No newline at end of file

commit eb4de2a9826332633c62e44a1a130d9b1a88171a (main)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    init flag printer

diff --git a/flag.py b/flag.py
new file mode 100644
index 0000000..77d6cec
--- /dev/null
+++ b/flag.py
@@ -0,0 +1 @@
+print("Printing the flag...")
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ git checkout feature/part-3
Cambiado a rama 'feature/part-3'
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes/drop-in$ git log -p flag.py
commit 1308521d0d0b66df1a73e91d5d9e2d74610002e3 (HEAD -> feature/part-3)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    add part 3

diff --git a/flag.py b/flag.py
index 77d6cec..78ac69c 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,3 @@
 print("Printing the flag...")
+
+print("w0rk_e4b79efb}")

commit eb4de2a9826332633c62e44a1a130d9b1a88171a (main)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    init flag printer

diff --git a/flag.py b/flag.py
new file mode 100644
index 0000000..77d6cec
--- /dev/null
+++ b/flag.py
@@ -0,0 +1 @@
+print("Printing the flag...")

result = picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_e4b79efb}

```
## Referencias
unzip --> para desempaquetar archivos .zip
cat -->para ver el contenido de archivos
git log -p (archivo) -->comando para ver los cambios de un archivo en comits que lo han modificado.
git checkout (rama) --> para cambiar rama que es otro medio de carga de datos