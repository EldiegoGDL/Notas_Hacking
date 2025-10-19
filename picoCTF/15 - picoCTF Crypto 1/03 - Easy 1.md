## Descripción
The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.
## Solución
```
CRYPTOISFUN

---------------------

picoCTF{CRYPTOISFUN}
```
## Notas adicionales
+ con wget descargamos el archivo que proporcionan
+ hay dos formas de resolverlo con el mismo metodo
+ manual mente hacemos un cat al archivo tabla.txt
+ usamos `UFJKXQZQUNB` como eje X y a `SOLVECRYPTO` como eje Y
+ sabiendo lo anterior buscamos los cruces en la tabla y asi vamos formando la bandera
+ o podemos ir a la pagina de ciberchef para que sea mas automatica la busqueda `UFJKXQZQUNB` como input y `SOLVECRYPTO` como llave
+ de esas dos formas conguimos lo mismo la bandera
## Referencias