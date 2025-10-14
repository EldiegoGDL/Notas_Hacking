## Descripción
We found this [file](https://mercury.picoctf.net/static/da18eed3d15fd04f7b076bdcecf15b27/tunn3l_v1s10n). Recover the flag.
## Solución
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/tunn3l_v1s10n]
└─$ hexeditor tunn3l_v1s10n 
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/tunn3l_v1s10n]
└─$ xxd -s 0xc -l 4 tunn3l_v1s10n
0000000c: 0000 2800
```

```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/tunn3l_v1s10n]
└─$ xxd -s 0x14 -l 4 tunn3l_v1s10n
00000014: 0000 6e04   
```

![[Pasted image 20251013184911.png]]
picoCTF{qu1t3_a_v13w_2020}
## Notas adicionales
+ con wget descargamos el archivo
+ al intentar abrirlo observamos que la imagen es una bmp y esta dañada
+ al ver que esta dañado el archivo usamos el comando hexeditor para analizarlo a profundidad
+ corregimos el encabezado
+ despues corregimos modificamos la altura ya que esta se encuentra muy ancha la imagen en el offset 0x12

## Referencias