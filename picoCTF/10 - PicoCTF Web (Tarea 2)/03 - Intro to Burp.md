
## Descripcion
* Additional details will be available after launching your challenge instance.
* Try using burpsuite to intercept request to capture the flag.
* Try mangling the request, maybe their server-side code doesn't handle malformed requests very well.

## Solucion

al abrir la pagina nos encontramos con un formulario al no encontar nada en la pagina ni en el codigo fuente intentamos usar la aplicacion burp al momento de rellenar los datos lo interceptamos para luego hacer un following al llegar a una autenticacion llenamos cualquier valor y despues mandamos la la respuesta al repeter al enviar los datos solo recibimos un codigo fuente sin pistas asi que en ves de querer recibir datos con GET intentamos poner en el encabezado un POST para enviar los datos y esto recibimos.
```
HTTP/1.1 200 OK
Server: Werkzeug/3.0.1 Python/3.8.10
Date: Mon, 06 Oct 2025 00:21:02 GMT
Content-Type: text/html; charset=utf-8
Content-Length: 105
Vary: Cookie
Connection: close

Welcome, acbs you sucessfully bypassed the OTP request. 
Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_9090d63c}
```
y asi encontramos la bandera
## Referencias: