## Descripción
There is some interesting information hidden around this site [http://mercury.picoctf.net:39698/](http://mercury.picoctf.net:39698/). Can you find it?
## Solución
al analisar el codigo fuente de la pagina solo observamos esto
```
<!doctype html>
<html>
  <head>
    <title>Scavenger Hunt</title>
    <link href="[https://fonts.googleapis.com/css?family=Open+Sans|Roboto](view-source:https://fonts.googleapis.com/css?family=Open+Sans|Roboto)" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="[mycss.css](view-source:http://mercury.picoctf.net:39698/mycss.css)">
    <script type="application/javascript" src="[myjs.js](view-source:http://mercury.picoctf.net:39698/myjs.js)"></script>
  </head>

  <body>
    <div class="container">
      <header>
		<h1>Just some boring HTML</h1>
      </header>

      <button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">How</button>
      <button class="tablink" onclick="openTab('tababout', this, '#222')">What</button>

      <div id="tabintro" class="tabcontent">
		<h3>How</h3>
		<p>How do you like my website?</p>
      </div>

      <div id="tababout" class="tabcontent">
		<h3>What</h3>
		<p>I used these to make this site: <br/>
		  HTML <br/>
		  CSS <br/>
		  JS (JavaScript)
		</p>
	<!-- Here's the first part of the flag: picoCTF{t -->
      </div>

    </div>

  </body>
</html>
```
abrimos los archivos del codigo fuente y en el .css esto encontramos al final

```
/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */
```


despues agregamos robots.txt a la url y esto es lo que encontramos

```
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?
```
asi que al revisar en la pagina apaches podemos apreciar que hay una forma de acceder a unos archivos de la pagina web siempre que se trate de un servidor apache.
![[Pasted image 20250923235959.png]]

lo metemos a la url para comprobar.
![[Pasted image 20250924000114.png]]
y obtenemos
```
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.
```

y ahora intentamos con .DS_STORE que almacena la configuracion de la carpeta en el servidor
```
Congrats! You completed the scavenger hunt. Part 5: _fa04427c}
```

ya para el final juntamos todas las partes y asi obtubimos la bandera

picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_fa04427c}
## Referencias
.htaccess Apache Server : [https://httpd.apache.org/docs/2.4/en/howto/htaccess.html](https://httpd.apache.org/docs/2.4/en/howto/htaccess.html "https://httpd.apache.org/docs/2.4/en/howto/htaccess.html")
.DS_Store mac file: [https://en.wikipedia.org/wiki/.DS_Store](https://en.wikipedia.org/wiki/.DS_Store "https://en.wikipedia.org/wiki/.DS_Store")
