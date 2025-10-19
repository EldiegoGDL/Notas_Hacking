## Descripción
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext).
## Solución
```
crossingtherubicondjneoach
----

picoCTF{crossingtherubicondjneoach}
```

## Notas adicionales
+ con wget descargamos el archivo
+ usamos ciberchef con la seccion ROT13 y pegamos el texto
+ al ver que lo que conseguimos no es la badera la pagina en ROT13 tiene la opcion de dar un numero de vueltas al desincriptado esto se refiere a cuantas veces se va a volver a desincriptar asi que aumentamos el numero hasta que demos con la bandera
+ y en la vuelta 22 conseguimos una bandera coherente
## Referencias