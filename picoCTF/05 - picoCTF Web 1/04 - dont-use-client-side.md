## Descripción
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/17682/` ([link](https://jupiter.challenges.picoctf.org/problem/17682/)) or http://jupiter.challenges.picoctf.org:17682
## Solución
inspeccionamos la pagina y podemos llegar a observer un ciclo if que nos da la contraseña al checarla por partes pero estas partes vienen en un orden.

1- pico
2- CTF{
3- no_c
4- lien
5- ts_p
6- lz_b
7- 706c
8- 5}
luego de ordenarlas las juntamos y asi conseguimos la bandera

paswword = picoCTF{no_clients_plz_b706c5}
## Referencias
ciclos y condiciones IF
html --> [¿Qué es el protocolo HTTPS y para qué sirve? Guía completa](https://www.siteground.es/blog/que-es-https-y-para-que-sirve-guia-completa/)