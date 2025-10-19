## Descripción
I found this cipher in an old book. Can you figure out what it says? Connect with `nc jupiter.challenges.picoctf.org 32411`.
## Solución
```

For the implementation of this cipher a table is formed by sliding the lower half of an ordinary alphabet for an apparently random number of places with respect to the upper halfpicoCTF{b311a50_0r_v1gn3r3_c1ph3r7b996649}

picoCTF{b311a50_0r_v1gn3r3_c1ph3r7b996649}

```
## Notas adicionales
+ nos conectamos al nc que nos proporcionaron
+ al conectarnos nos muestran un mensaje y automaticamente nos desconectamos
+ tomando en cuenta el mesnaje lo copiamos
+ usamos una pagina https://www.guballa.de/vigenere-solver para encontrar la llave del encriptado
+ al saber que "flag" es la llave nos dirigimos a ciberchef y a la seccion vigenere decode ponemos la llave y el texto para desincriptarlo
+ al leer el texto desincriptado conseguimos la bandera
## Referencias
https://www.guballa.de/vigenere-solver