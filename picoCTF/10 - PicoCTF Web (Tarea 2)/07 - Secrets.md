#  - Secrets

## Descripcion:
* We have several pages hidden. Can you find the one with the flag?
Additional details will be available after launching your challenge instance.
* folders folders folders

## Solucion
en la pagina lo primero revisamos el codigo fuente y  encontramos una url que termina con secret
```
<!DOCTYPE html>
<html>
  <head>
    <title></title>
    <link rel="stylesheet" href="[hidden/file.css](view-source:http://saturn.picoctf.net:54938/secret/hidden/file.css)" />
  </head>

. . .

```
y alli habia otra carpeta llamada hidden asi que nos movemos alli
```
<!DOCTYPE html>
<html>
  <head>
    <title>LOGIN</title>
    <!-- css -->
    <link href="[superhidden/login.css](view-source:http://saturn.picoctf.net:54938/secret/hidden/superhidden/login.css)" rel="stylesheet" />
  </head>
  <body>
    <form>
...
```
y encontramos otra carpeta superhidden la seguimos
```
<!DOCTYPE html>
<html>
  <head>
    <title></title>
    <link rel="stylesheet" href="[mycss.css](view-source:http://saturn.picoctf.net:54938/secret/hidden/superhidden/mycss.css)" />
  </head>

  <body>
    <h1>Finally. You found me. But can you see me</h1>
    <h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_51b260fe}</h3>
  </body>
</html>
```
y asi encontramos la bandera
## Referencias: