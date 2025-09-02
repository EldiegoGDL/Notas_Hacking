## Descripción

Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 14291`.
## Solución


```
DiegoGDL-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 14291 | grep "picoCTF"
picoCTF{digital_plumb3r_ea8bfec7}
```
## Referencias

use un pipes para que con el carácter | mas el comando Grep se filtre la salida con el mismo patron de texto