## Descripción

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.
## Solución
pegamos la conexion netcat y su puerto al darnos diferentes conjuntos de datos encriptados los desincriptamos y respondemos los inputs hasta dar con la llave
````
DiegoGDL-picoctf@webshell:~$  nc jupiter.challenges.picoctf.org 29221
Let us see how data is stored
submarine
Please give the 01110011 01110101 01100010 01101101 01100001 01110010 01101001 01101110 01100101 as a word.
...
you have 45 seconds.....

Input:
submarine
Please give me the  146 141 154 143 157 156 as a word.
Input:
falcon
Please give me the 636f6d7075746572 as a word.
Input:
computer
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_00a975ff}
````
## Referencias
ASCII
HEXADECIMAL
BINARYO