## Descripción
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.
To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!
Find the PCAP file here Network Traffic PCAP file and try to get the flag.
## Solución
```
partes de la bandera:
 - cGljb0NURg==

 - ezF0X3c0cw==

 - bnRfdGg0dA==

 - XzM0c3lfdA==

 - YmhfNHJfZQ==

 - NWU4Yzc4ZA==
   
 - fQ==
 
"picoCTF"
"{1t_w4s"
"nt_th4t"
"_34sy_t"
"bh_4r_e"
"5e8c78d"
"}"

bandera
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_e5e8c78d}
```
## Notas adicionales
+ con wget descargamos el archivo
+ como este es un archivo.pcap
+ lo abrimos con wireshark
+ al ver que en cada registro el recuadro que muestra los bites se aprecia un fragmento de texto en base64
+ asique lo decodificamos el primero que encontramos hasta arriba para saber que contiene
+ al desincriptar uno de estos nos da otro texto base64 y al volverlo a desoncriptar da el encabezado picoCTF
+ asique lo hacemos con los demas registros
+ tambien aprecie que los textos con el tamaño de 12 caracteres esos tienen los datos dobles base64
+ pero faltaron partes asique usamos hexeditro mas ctrl + E para verlos textos y extraer mas facil los textos
+ ya solo falta armar la bandera con solo lo que se puede llegar a entender
## Referencias
