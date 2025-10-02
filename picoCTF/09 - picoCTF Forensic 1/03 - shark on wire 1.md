## Descripción

## Solución
primero con wget descargamos el archivo.pcap

despues usamos el programa wireshark o usamos el comando wireshark para que lo abra desde la terminal
```c
wireshark captura.pcap
```
nos desplegara una gran lista de paquetes (fechas,maquina,protocolos,longitud,informacion,etc)
![[Pasted image 20251002084222.png]]
tomamos el paquete UDP con un follow y luego UDP-String
![[Pasted image 20251002084336.png]]
al estar recorriéndolas podemos ver la informacion de los registros y asi logramos encontrar la bandera
![[Pasted image 20251002084424.png]]
porlo que se ve estaba en la secuencia 6
## Referencias
archivos.pcap --> es un formato de archivo que almacena capturas de tráfico de red para análisis y diagnóstico de redes
wireshark -->es un analizador de paquetes que permite examinar la información que viaja por redes locales o de área amplia, ya sea vía Ethernet, Wi-Fi, Bluetooth o interfaces virtuales como Docker