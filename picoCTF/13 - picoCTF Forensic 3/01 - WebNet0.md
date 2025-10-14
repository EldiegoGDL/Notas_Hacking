## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.
## Solución
```
HTTP/1.1 200 OK

Date: Fri, 23 Aug 2019 15:56:36 GMT

Server: Apache/2.4.29 (Ubuntu)

Last-Modified: Mon, 12 Aug 2019 16:47:05 GMT

ETag: "62-58fee462bf227-gzip"

Accept-Ranges: bytes

Vary: Accept-Encoding

Content-Encoding: gzip

Pico-Flag: picoCTF{nongshim.shrimp.crackers}

Content-Length: 100

Keep-Alive: timeout=5, max=100

Connection: Keep-Alive

Content-Type: text/css
```
## Notas adicionales
+ con wget descargamos los archivos picopico.key y el archivo capture.pcap
+ despues con wireshark abrimos el archivo .pcap
+ al ver que la transaccion TLS no sirve usamos la llave que nos dieron configurando el wireshark
+ buscamos en edicion y luego preferencias y nos movemos a protocolos 
+ para luego seleccionar TLS y en el apartado editar seleccionamos file para que abra nuestra llave y asi desincripte las transacciones TLC aplicamos los cambios
+ nos dirigimos a los registros y hacemos un seguimiento a un TLS stream y al volver a analizar las transacciones desincriptadas encontramos la solucion
## Referencias