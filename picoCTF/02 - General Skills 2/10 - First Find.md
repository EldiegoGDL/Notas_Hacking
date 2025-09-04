## Descripción
Unzip this archive and find the file named 'uber-secret.txt'
## Solución
primero con el wget cargamos el zip al sistema con unzip lo desempaquetamos en una carpeta para poder acceder a su contenido sabiendo como se llama el archivo que buscamos usamos un comando que buscara en todas las carpetas el archivo por su nombre.

```
DiegoGDL-picoctf@webshell:~$ ls
README.txt  files  files.zip
DiegoGDL-picoctf@webshell:~$ cd files
DiegoGDL-picoctf@webshell:~/files$ ls
13771.txt.utf-8  14789.txt.utf-8  acceptable_books  adequate_books  satisfactory_books
DiegoGDL-picoctf@webshell:~/files$ find . -name uber-secret.txt
./adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
DiegoGDL-picoctf@webshell:~/files$ cd adequate_books/more_books/.secret/deeper_secrets/deepest_secrets
DiegoGDL-picoctf@webshell:~/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets$ ls
uber-secret.txt
DiegoGDL-picoctf@webshell:~/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets$ cat uber-secret.txt
picoCTF{f1nd_15_f457_ab443fd1}
```

## Referencias

find . -name "nombre del archivo" --> es un comando que nos ayuda a buscar un archivo en todas las carpetas por su nombre