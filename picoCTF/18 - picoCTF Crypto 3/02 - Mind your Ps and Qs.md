## Descripción
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/3cfeb09681369c26e3f19d886bc1e5d9/values)
## Solución
```
c = 8533139361076999596208540806559574687666062896040360148742851107661304651861689
n = 769457290801263793712740792519696786147248001937382943813345728685422050738403253
e = 65537  

# se obtienen de la factorizacion
p = 1617549722683965197900599011412144490161
q = 475693130177488446807040098678772442581573

tn = (p-1) * (q-1)

d = pow(e, -1, tn)

m = pow(c,d,n)

flag = bytes.fromhex(hex(m)[2:]).decode()

print(flag)
```
picoCTF{sma11_N_n0_g0od_45369387}

## Notas adicionales
+ con wget descargamos el archivo que nos proporcionaron 
+ con file revisamos que tipo de archivo es y se trata de un texto en codigo ASCii 
+ con un cat sacamos los valores que este contiene
+ y sabiendo su contenido hacemos un codigo en python para manipular los valores segun lo que se requiere para conseguir el texto encriptado
+ como nos pide p y q para seguir con la formula usamos una pagina para factorizar n para que esta se divida en p y q
+ y con m desicnriptado nos dan la bandera
## Referencias
https://factordb.com