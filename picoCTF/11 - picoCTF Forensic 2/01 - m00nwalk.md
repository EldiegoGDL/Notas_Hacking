## Descripción
Decode this [message](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) from the moon.
## Solución
con wget descargamos el archivo y con file revisamos que tipo de archivo se trata
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/m00nwalk]
└─$ file message.wav                                         
message.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 48000 Hz

```
al ver que es un archivo de audio instalamos un decodificador de un repositorio de github
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/m00nwalk]
└─$ cd /opt
┌──(diego㉿Maquina-deGuerra)-[/opt]
└─$ sudo git clone https://github.com/colaclanth/sstv
[sudo] contraseña para diego: 
Clonando en 'sstv'...
remote: Enumerating objects: 221, done.
remote: Counting objects: 100% (59/59), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 221 (delta 51), reused 49 (delta 49), pack-reused 162 (from 1)
Recibiendo objetos: 100% (221/221), 1.01 MiB | 2.37 MiB/s, listo.
Resolviendo deltas: 100% (139/139), listo.
```
y instalamos el setup.py en la carpeta sstv para despues regresar a nuestra carpeta con el archivo .wav
```
┌──(diego㉿Maquina-deGuerra)-[/opt/sstv]
└─$ sudo python3 setup.py intall
┌──(diego㉿Maquina-deGuerra)-[/opt/sstv]
└─$ cd     
┌──(diego㉿Maquina-deGuerra)-[~]
└─$ cd Documentos/forensic/m00nwalk 
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/m00nwalk]
└─$ 
```
y procedemos a ejecutar el decodificador con el archivo de audio y lo guardamos en un png
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/m00nwalk]
└─$ sstv -d message.wav -o flag.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [###############################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!

```
y abrimos la imagen para encontrarnos con la bandera
![[Pasted image 20251006161930.png]]
picoCTF{beep_boop_im_in_space}
## Referencias 
decodificador https://github.com/colaclanth/sstv