## Descripción

There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 43239`, but it doesn't speak English...
## Solución

tomamos la conexión netcat y la pegamos en la terminal luego nos mostrara un conjunto números separados.

```
DiegoGDL-picoctf@webshell:~$ nc mercury.picoctf.net 43239
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
55 
99 
48 
56 
50 
49 
102 
53 
125 
10 
```


estos los tomamos en cuenta y comparamos en una tabla de codigo ascii para traducir cada numero mostrado anteriormente la tabla la logre encontrar en una pagina web donde al traducirlo me die este resultado.
picoCTF{g00d_k1tty!_n1c3_k1tty!_7c0821f5}

## Referencias

[El código ASCII Completo, tabla con los codigos ASCII completos, caracteres simbolos letras ascii, ascii codigo, tabla ascii, codigos ascii, caracteres ascii, codigos, tabla, caracteres, simbolos, control, imprimibles, extendido, letras, vocales, signos, simbolos, mayusculas, minusculas, alt, teclas, acentos, agudo, grave, eñe, enie, arroba, dieresis, circunflejo, tilde, cedilla, anillo, libra, esterlina, centavo, teclado, tipear, escribir, español, ingles, notebook, laptop, asccii, asqui, askii, aski,20250902](https://elcodigoascii.com.ar/)
