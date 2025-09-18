## Descripción
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/28921/` ([link](https://jupiter.challenges.picoctf.org/problem/28921/)) or http://jupiter.challenges.picoctf.org:28921
## Solución

la pagina al querer dar boton a flag nos indica que no somos picobrowser y que somos otra maquina para engañar a la pagina nos vamos a la terminal y usamos el siguente codigo para que nos de la bandera.

curl https://jupiter.challenges.picoctf.org/problem/28921/flag -H "User-Agent:picobrowser" | grep pico

```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ curl https://jupiter.challenges.picoctf.org/problem/28921/flag -H "User-Agent:picobrowser"  | grep pico
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  2115  100  2115    0     0   5749      0 --:--:-- --:--:-- --:--:--  5778
         <!-- <strong>Title</strong> --> picobrowser!
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}</code></p>

```
lo que hicimos es que forzamos un acceso enviando a la pagina que accedimos como picobrowser y asi con un grep filtramos donde se encontraba la bandera
## Referencias

curl --> es una herramienta de línea de comandos que permite transferir datos hacia y desde servidores utilizando diversos protocolos como HTTP, HTTPS, FTP y más
https --> [¿Qué es el protocolo HTTPS y para qué sirve? Guía completa](https://www.siteground.es/blog/que-es-https-y-para-que-sirve-guia-completa/)
html
grep --> buscador por medio de filtrado de una palabra