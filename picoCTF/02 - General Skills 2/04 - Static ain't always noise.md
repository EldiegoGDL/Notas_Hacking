## Descripción
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static)? This [BASH script](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/ltdis.sh) might help!
## Solución

volvemos a cargar los archivos con wget y luego
con cat + el nombre del script podemos ver su codigo interno para saber que es lo que hará

```
DiegoGDL-picoctf@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_1e6a7731}
```
## Referencias

cat + script : para ver su codigo