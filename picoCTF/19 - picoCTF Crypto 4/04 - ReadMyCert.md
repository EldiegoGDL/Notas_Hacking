## Descripción
How about we take you on an adventure on exploring certificate signing requestsTake a look at this CSR file [here](https://artifacts.picoctf.net/c/420/readmycert.csr).
## Solución
```
openssl req -in readmycert.csr -noout -text

┌──(diego㉿Maquina-deGuerra)-[~/Documentos/Crypto/ReadMyCert]
└─$ openssl req -in readmycert.csr -noout -text
Certificate Request:
    Data:
        Version: 1 (0x0)
        Subject: CN=picoCTF{read_mycert_a7163be8}, name=ctfPlayer
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption



echo "sdflasd" | base64 -d | strings | grep pico
```

picoCTF{read_mycert_a7163be8}
## Notas adicionales
+ con wget descargamos el archivo que nos proporcionaron
+ con file revisamos que se trata de un nuevo tipo de archivo .csr
+ con un cat observamos un codigo en base64 
+ al desincriptarlo con ciberchef conseguimos la bandera
## Referencias
openssl es una herramienta para trabajar con ssl,certificados y solicitudes de certificacion
