## Descripción
This service provides you an encrypted flag. Can you decrypt it with just N & e?Connect to the program with netcat:`$ nc verbal-sleep.picoctf.net 64306`The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_verbal_sleep/b1999e70e98a4fb11d441bd4ef60a948c1ae4a27a3a7154ed2678990b91f52e4/encrypt.py).
## Solución
```python
n= 16775679412627339608347549938561177223699090366289871622319738256760846721236777795243197398128726830037986453839106993151667639754578184366642900161451814

e= 65537

c= 11380988167549819609728027628441656501585538643064242112061878465115736163300602993656619913605373633733210005571021986550026689389355755071298322956206337

  
  

# se obtienen de la factorizacion

p = n// 2

q = 0

  

tn = (p-1) * (q-1)

  

d = pow(e, -1, tn)

  

m = pow(c,d,n)

  

flag = bytes.fromhex(hex(m)[2:]).decode()

  

print(flag)
```
picoCTF{tw0_1$_pr!m305af7255}
## Notas adicionales
+ nos conectamos  la conexion nc
+ al entrar nos dan los valores de n,e y c
+ como no podemos factorizar a n
+ lo dividimos y asi sacamos la factorizacion mas cercana y a q lo tomamos como cero ya que no afectara en nada
## Referencias
