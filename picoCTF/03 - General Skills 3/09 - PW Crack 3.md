## Descripción
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/16/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/16/level3.hash.bin) in the same directory too. There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script
## Solución
cargamos los archivos del problema con wget para luego ejecutar el programa al ver que ocupa una contraseña que desconocemos accedemos al codigo fuente con el comando nano para que al ver que tenemos 7 posibles llaves de desincriptado hacemos un ciclo for para que pruebe cada una y luego imprimimos los resultados aunque no sepamos la contraseña del sistema.

```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ nano level3.py
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ python3 level3.py
Please enter correct password for flag: s
That password is incorrect
~fo=M[J)c;9:Qi`c`h=<iP>0>8>37?q
{>52H&fcc5T1:le0g3d?;`d<2g+
.o7iR}32an`870aeh9Yfdn1fgg6)
|=g=OB)a`1:S2hcb35<k
                    60<c635dy
-<d=A)0a2:3kc326<:
50mb53dez
|:`<OE(ag6;S5obb42=k
                    11<d125c~
picoCTF{m45h_fl1ng1ng_2b072a90}

```

## Referencias
wget --> para cargar documentos
python3 --> para ejecutar archivos.py
nano --> para poder editar archivos
principios de ciclos for