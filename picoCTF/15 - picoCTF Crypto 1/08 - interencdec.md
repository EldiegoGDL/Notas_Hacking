## Descripción
Can you get the real meaning from this file. Download the file [here](https://artifacts.picoctf.net/c_titan/108/enc_flag).
## Solución
```
wpjvJAM{jhlzhy_k3jy9wa3k_h47j6k69}

ROT13 vuelta {19}:

picoCTF{caesar_d3cr9pt3d_a47c6d69}
```

## Notas adicionales
+ con wget descargamos el archivo
+ despues con cat lo abrimos
+ al ver que es un texto en base64 lo decodificamos
+ al ver que no tiene sentido lo volvemos a decodificar
+ y al ver que ya nos dio un texto que al decoficiarlo este se rompio cambiamos de metodo de decodificado
+ ahora con el ultimo texto que decodificamos usamos ROT13 con las vueltas necesarias
+ en la vuelta 19 conseguimos la bandera
## Referencias
