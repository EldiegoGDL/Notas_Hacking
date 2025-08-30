
## Descripción

What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases

## Solución

```python
import base64

encriptado = "bDNhcm5fdGgzX3IwcDM1"

print( base64.b64decode(encriptado).decode('utf-8'))

## salida {l3arn_th3_r0p35}
```

picoCTF{l3arn_th3_r0p35}
## Referencias
usamos la libreria base64 para usar su funcion decode