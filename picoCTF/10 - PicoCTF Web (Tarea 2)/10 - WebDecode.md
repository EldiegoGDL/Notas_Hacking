## Descripcion:
Do you know how to use the web inspector? Start searching [here](http://titan.picoctf.net:64232/) to find the flag

## Solucion:
nos encontramos una pagina que directamente el reto dicta que revisemos el codigo fuente
y al estar indagando en la url
view-source:http://titan.picoctf.net:64232/about.html
encontramos un texto encriptado
```
<section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMWY4MzI2MTV9">

que en base64 quedaria como:
picoCTF{web_succ3ssfully_d3c0ded_1f832615}
```
y asi obtuvimos la bandera
## Referencias: