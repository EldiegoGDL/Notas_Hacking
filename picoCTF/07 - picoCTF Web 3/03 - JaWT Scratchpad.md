## Descripción
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864
## Solución
en la pagina intentamos loguearnos como admin al recibir un mesnaje que no nos deja ser admin nos logueamos con otro nombre, despues sacamos el jws el toke que nos dio la pagina.

pero primero descomprimimos el archivo rockyou para despues usar el comando john para que genero un nuevo token

```
┌──(diego㉿Maquina-deGuerra)-[~]
└─$ cd /usr/share/wordlists/                                               
    
┌──(diego㉿Maquina-deGuerra)-[/usr/share/wordlists]
└─$ sudo gzip -d rockyou.txt.gz

┌──(diego㉿Maquina-deGuerra)-[~]
└─$ john token -w=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:06 DONE (2025-09-26 09:17) 0.1652g/s 1222Kp/s 1222Kc/s 1222KC/s ilovepinky53..ilovepatri
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 

```

nos dirigimos al jws debugger y modificamos el payload como admin ponemos la palabra crakeada  en la firma y copiamos el token que generamos y recargamos la pagina

![[Pasted image 20250926092855.png]]
![[Pasted image 20250926100235.png]]
## Referencias
- JSON: [https://en.wikipedia.org/wiki/JSON](https://en.wikipedia.org/wiki/JSON "https://en.wikipedia.org/wiki/JSON"),
- JWT : [https://jwt.io/introduction](https://jwt.io/introduction "https://jwt.io/introduction"),
- jwt debugger : [https://jwt.lannysport.net/](https://jwt.lannysport.net/ "https://jwt.lannysport.net/"),
- john : [https://github.com/openwall/john](https://github.com/openwall/john "https://github.com/openwall/john")