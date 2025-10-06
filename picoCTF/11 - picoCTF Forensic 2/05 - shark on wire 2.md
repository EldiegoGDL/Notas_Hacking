## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
## Solución
con wget descargamos el archivo y con file revisamos que tipo de archivo es
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/shark_on_wire_2]
└─$ wget https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/shark_on_wire_2]
└─$ file capture.pcap 
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)

```
ahora lo abrimos con wireshark y seguimos las columnas con udp
![[Pasted image 20251006162526.png]]
observamos que esta desplegada en varios registros y que en el registro 32 hay una palabra que dice "beging" y en la 60 "end" por ello instalaremos un paquete de python3
```
|──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/shark_on_wire_2]
└─$ sudo apt install python3-scapy 
```
para luego programar un exploit que nos de la bandera
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/shark_on_wire_2]
└─$ nano exploid.py 
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/shark_on_wire_2]
└─$ cat exploid.py       
```
```python
from scapy.all import *

packets = rdpcap('capture.pcap')

flag=''

for p in packets:
    if UDP in p and p[UDP].dport == 22:
        if p[UDP].sport > 5000:
            flag+=chr(p[UDP].sport - 5000)

print(flag) 
```
y lo ejecutamos para obtener la bandera
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/shark_on_wire_2]
└─$ python3 exploid.py      
picoCTF{p1LLf3r3d_data_v1a_st3g0}

```

## Referencias