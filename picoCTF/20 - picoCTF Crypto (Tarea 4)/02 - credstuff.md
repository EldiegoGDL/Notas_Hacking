## Descripción
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it?Download the leak [here](https://artifacts.picoctf.net/c/151/leak.tar).The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.
## Solución
cvpbPGS{P7e1S_54I35_71Z3}
desincriptado con ROT13
picoCTF{C7r1F_54V35_71M3}

## Notas adicionales
+ con wget descargamos el archivo.tar
+ al ser un nuevo tipo de archivo investigamos sobre este
+ al ver que se trata de un nuevo tipo de metodo de comprimir archivos usamos su respectivo comando para extraer los datos
+ al crear una carpeta con su contenido la abrimos
+ y como estos solo muestra usuarios y contraseñas encriptadas abrimos ambos archivos para analizar linea por linea empezando por usuarios
+ con el buscador encontramos en que linea esta el usuario que buscamos "cultiris"
+ despues nos pasamos al archivo de contraseñas y al comparar ambos archivos logramos ver que tienen el mismo numero de lineas
+ por ello deducimos que se alinean segun usuario y contraseña
+ sabiendo esto y que el usuario cultiris esta en la linea 378
+ buscamos la linea 378 en el archivo passwords
+ y nos encontramos una texto como los otros encriptado y este cumple con el formallo de llaves {  } = cvpbPGS{P7e1S_54I35_71Z3}
+ con base64 no funciona asi que probamos ROT13
+ y asi conseguimos la bandera
## Referencias
