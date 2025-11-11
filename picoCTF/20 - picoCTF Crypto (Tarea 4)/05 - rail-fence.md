## Descripción
A type of transposition cipher is the rail fence cipher, which is described [here](https://en.wikipedia.org/wiki/Rail_fence_cipher). Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it?Download the message [here](https://artifacts.picoctf.net/c/188/message.txt).Put the decoded message in the picoCTF flag format, `picoCTF{decoded_message}`.
## Solución

Ta _7N6D49hlg:W3D_H3C31N__A97ef sHR053F38N43D7B i33___N6  
{ 
carril 1
carril 2
carril 2
carril 4 
}

= The flag is: WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_4A76B997

picoCTF{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_4A76B997}
## Notas adicionales
+ con wget descargamos los archivos
+ el mensaje parece ser un texto que ni base64 ni ROT13 detectan pero al leer la descripcion del reto este nos da un link de una pagina que menciona una encriptacion curiosa que parece que consta de saltar entre renglones los caracteres
+ sabiendo el nombre del metodo de encriptacion nos vamos a ciber chef para decodificarlo teniendo en cuenta que el reto menciona 4 carriles
+ al llegar a ciberchef y configurar la referencia de 4 carriles obtenemos la bandera
## Referencias
