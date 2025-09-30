## Descripción
How about trying to match a regular expressionThe website is running [here](http://saturn.picoctf.net:57345/).
## Solución
lo primero que nos topamos es con una interfas con una caja de texto
![[Pasted image 20250930133358.png]]
al escribir cualquier texto nos salta un mensaje de error
![[Pasted image 20250930133428.png]]
pero si intentamos escribir picoCTF en la caja de texto nos dan un mensaje de la pagina con la bandera
![[Pasted image 20250930133532.png]]
para saber porque coincidió revisamos el codigo fuente y encontramos un script js.
```
<script>
	function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}

</script>
```
en este se observa un comentario con el texto ^p . . . . . F!
en la pagina [RegExr: Learn, Build, & Test RegEx](https://regexr.com/)
podemos poner dicho texto y nos indica que el carácter "." puede ser cualquier valor siempre que empiece con p y termine con F por eso la palabra picoCTF funciono aun asi cual quiera con las especificaciones requeridas de p y F funcionaba.

![[Pasted image 20250930134744.png]]

## Referencias
[RegExr: Learn, Build, & Test RegEx](https://regexr.com/)