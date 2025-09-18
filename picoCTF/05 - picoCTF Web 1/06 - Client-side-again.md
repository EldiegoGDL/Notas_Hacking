## Descripción
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/56816/` ([link](https://jupiter.challenges.picoctf.org/problem/56816/)) or http://jupiter.challenges.picoctf.org:56816
## Solución
primero intentamos cual quier contraseña al ver que solo hay un mensage de acceso denegado inspeccionamos el codigo de la pagina alli solo sogramos ver un codigo de javascript que se encuentra poco legible lo copiamos y usamos la pagina JS Nice para que lo acomode al poder ver bien el codigo extraemos el valor "_0x5a46" donde se encuentra la bandera revuelta_
![[Pasted image 20250918121239.png]]
luego de obtener la variable nos vamos a la consola del inspector y escribimos la variable completa y luego el nobre de la variable y una posicion de esa forma vamos armando la bandera.
 ![[Pasted image 20250918121516.png]]
## Referencias
[JS NICE: Statistical renaming, Type inference and Deobfuscation](http://jsnice.org/)
htpps --> [¿Qué es el protocolo HTTPS y para qué sirve? Guía completa](https://www.siteground.es/blog/que-es-https-y-para-que-sirve-guia-completa/)