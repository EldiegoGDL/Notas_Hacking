## Descripcion:
* Can you get the flag?
Additional details will be available after launching your challenge instance.
* Do you know how to modify cookies?

## Solucion

nos encontamos con una pagina que solo tiene un boton que manda a otra pagina pero solo con un texto asi que revisamos el codigo fuente y solo encontremos un archivo.js
```
function continueAsGuest()
{
  window.location.href = '/check.php';
  document.cookie = "isAdmin=0";
}
```
por lo visto hay una documentacion que hace referencia de una cookie con admin como 0 esto lo tomaremos en cuenta mas adelante.
usaremos burp para interceptarlo y mandarlo al repeter y cambiaremos el valor de la cookie para asi ser admin.
```
HTTP/1.1 200 OK
Server: nginx
Date: Mon, 06 Oct 2025 00:53:58 GMT
Content-Type: text/html; charset=UTF-8
Connection: keep-alive
Vary: Accept-Encoding
Content-Length: 79





<html>
<body>



<p>picoCTF{gr4d3_A_c00k13_5d2505be}</p>


</body>
</html>

```
y asi sacamos la bandera
## Referencias: