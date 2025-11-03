## Descripción
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/127/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
## Solución
``` python
numeros = open('message.txt').read().split() 
flag = ' ' 
for numero in numeros: 
	mod = int(numero) % 37 
	if mod>=0 and mod<=25: 
		c = chr(mod+65) 
	elif mod>=26 and mod<=35: 
		c = chr(mod+22) 
	elif mod==36: 
		c = '_' 
	flag += c 
print(flag)
```

picoCTF{R0UND_N_R0UND_79C18FB3}
## Notas adicionales
+ primero usamos wget para descargar el texto encriptado
+ para luego generar un código que llegue a desencriptar el mensaje ya que es la bandera
+ al lograr desencriptar la bandera la introducimos al formato ya si conseguimos la bandera completa
## Referencias