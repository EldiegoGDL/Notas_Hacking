## Descripción
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?
You can download the challenge files here:
challenge.zip
The same files are accessible via SSH here:
ssh -p 54227 ctf-player@atlas.picoctf.net
Using the password 6abf4a82. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
## Solución

```
ctf-player@challenge:~/drop-in$ zbarimg flag.png 
Connection Error (Failed to connect to socket /var/run/dbus/system_bus_socket: No such file or directory)
Connection Null
QR-Code:picoCTF{p33k_@_b00_7843f77c}
scanned 1 barcode symbols from 1 images in 0.01 seconds

```


picoCTF{p33k_@_b00_7843f77c}
## Notas adicionales
+ accedemos a la conexion ssh
+ y nos dan una imagen de un codigo QR 
+ entoces revisamos si hay mas carpetas ocultas hacemos un ls -la
+ al hacer el ls -la nos topamos con los permisos anexados a la imagen asique sabiendo esto usamo un comando llamado zbarimg 
+ que decodifica el codigo QR
+ y nos da la bandera
## Referencias
zbarimg = es  un comando para leer codigos de barra y codigos qr de imagenes