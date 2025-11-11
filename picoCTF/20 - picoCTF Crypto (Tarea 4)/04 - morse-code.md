## Descripción
Morse code is well known. Can you decrypt this?Download the file [here](https://artifacts.picoctf.net/c/79/morse_chal.wav).Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.
## Solución
![[Pasted image 20251110165313.png]]
".-- .... ....- --... .... ....- --... .... ----. ----- -.. .-- ..--- ----- ..- ----. .... --..."

=  WH47H47H90DW20U9H7


.-- .... ....- --... ..--.- .... ....- --... .... ..--.- ----. ----- -.. ..--.- .-- ..--- ----- ..- ----. .... --...

= WH47_H47H_90D_W20U9H7

picoCTF{WH47_H47H_90D_W20U9H7}
## Notas adicionales
+ con wget descargamos el archivo
+ primero intentamos abrir el archivo al no poder
+ usamos el paquete sox
+ seleccionamos el archivo y lo volvemos una imagen de espectrograma
+ despues vamos a ciber chef y entendemos que por la imagen los sonidos cortos son puntos y los largos rayas
+ al primer intento no lo logramos asi que pasamos a windows para asi ya poder abrir el audio al ver que sacamos lo mismo 
+ volvemos a analizar el espectro grama y al leer el reto vemos que los espacios vacios del espectrograma el reto lo describe que lo tomemos en cuenta como guion bajo " _ "
+ con esto en cuenta corregimos y confirmamos que ya teniamos la bandera ya solo era agregar __ correctamente 
## Referencias
sox para hacer audios a morse en espectrogramas