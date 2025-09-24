## Descripción
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)

## Solución

revisamos primero el codigo fuente al ver que es una simulacion de un simple formulario.
entonces usamos el nuevo comando curl -x he intentamos los 3 envios de datos para ver como reacciona la pagina.

#### forma 1

```
┌──(diego㉿Maquina-deGuerra)-[~]
└─$ curl -X GET http://mercury.picoctf.net:28916/index.php                
Warning: Setting custom HTTP method to HEAD with -X/--request may not work 
Warning: the way you want. Consider using -I/--head instead.
                                                                         
┌──(diego㉿Maquina-deGuerra)-[~]
└─$ curl -X POST http://mercury.picoctf.net:28916/index.php                
Warning: Setting custom HTTP method to HEAD with -X/--request may not work 
Warning: the way you want. Consider using -I/--head instead.
                                                                             
┌──(diego㉿Maquina-deGuerra)-[~]
└─$ curl -I HEAD http://mercury.picoctf.net:28916/index.php HTTP/1.1 200 OK
curl: (6) Could not resolve host: HEAD
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}
Content-type: text/html; charset=UTF-8

```
#### forma 2
usamos un proxi para editar y meter un head en ves del get del proxi
![[Pasted image 20250922111614.png]]
![[Pasted image 20250922111636.png]]
## Referencias
proxy
curl (GET,POST,HEAD)--> es para cargar o enviar datos a una pagina web