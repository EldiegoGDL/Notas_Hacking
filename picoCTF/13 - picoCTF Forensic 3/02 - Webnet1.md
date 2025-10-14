## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.
## Solución
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/WebNet1]
└─$ strings vulture.jpg | grep pico 
picoCTF{honey.roasted.peanuts}

```
## Notas adicionales
+ con wget descargamos los archivos picopico.key y el archivo capture.pcap
+ despues con wireshark abrimos el archivo .pcap
+ al ver que la transaccion TLS no sirve usamos la llave que nos dieron configurando el wireshark
+ buscamos en edicion y luego preferencias y nos movemos a protocolos 
+ para luego seleccionar TLS y en el apartado editar seleccionamos file para que abra nuestra llave y asi desincripte las transacciones TLC aplicamos los cambios
+  nos dirigimos a los registros y hacemos un seguimiento a un TLS stream y al volver a analizar las transacciones desincriptadas encontramos una bandera que no sirve pero al final visualizamos que hay un texto encriptado que resulta ser una imagen
+ nos dirigimos a la opcion de archivos de wireshark y bajamos a exportar archivo https
+ y nos encontramos con la imagen que mensionaron en la transaccion asi que la exportamos y guardamos
+ al dirigirnos a la terminal realizamos un strings combinado con un grep para poder sacar la bandera
## Referencias