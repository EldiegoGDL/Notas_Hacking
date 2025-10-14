## Descripción
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg)
## Solución
```
┌──(diego㉿Maquina-deGuerra)-[~/…/Matryoshka_doll/base_images/base_images/base_images]
└─$ ls            
4_c.jpg  flag.txt
┌──(diego㉿Maquina-deGuerra)-[~/…/Matryoshka_doll/base_images/base_images/base_images]
└─$ cat flag.txt  
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32} 
```

## Notas adicionales
+ con wget descargamos la imagen que nos proporcionaron
+ despues instalaremos un nuevo paquete llamado binwalk
+ para luego usar el comando binwalk para saber si tiene mas datos anexados a la imagen
+ como este cuenta integrado dentro un zip lo descomprimimos con unzip
+ al descomprimirlo nos da otra imagen asi que la volvemos a analizar con binwalk
+ como este tambien tiene un zip integrado ciclamos el metodo hasta dar con la bandera
+ en la 4 imagen al descomprimirla nos da un archivo .txt con la bandera
## Referencias