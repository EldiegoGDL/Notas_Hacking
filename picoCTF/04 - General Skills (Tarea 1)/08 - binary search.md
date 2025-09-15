## Descripción
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses. Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools! You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/4/challenge.zip)

`ssh -p 53271 ctf-player@atlas.picoctf.net` Using the password `83dcefb7`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
## Solución
al hacer la conexion ssh nos dio como resultado un programa que se ejecuta inmediatamente de conectarse para ganar se ocupa adivinar un numero del 1 al 1000.

usando un radio de centenas ya que es mas facil descartar luego de saber el radio solo era adivinar de escala 1 a 100 y seguimos con decenas y por ultimo unidades esa es mi estratejia y funciono.

```
el-diego@Maquina-de-Guerra:~/Documentos/seguridad en redes$ ssh -p 53271 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 660
Lower! Try again.
Enter your guess: 650
Lower! Try again.
Enter your guess: 300
Higher! Try again.
Enter your guess: 500
Lower! Try again.
Enter your guess: 400
Lower! Try again.
Enter your guess: 350
Higher! Try again.
Enter your guess: 380
Higher! Try again.
Enter your guess: 390
Lower! Try again.
Enter your guess: 385
Congratulations! You guessed the correct number: 385
Here's your flag: picoCTF{g00d_gu355_ee8225d0}
Connection to atlas.picoctf.net closed.

```

## Referencias

escalas de centenas decenas unidades