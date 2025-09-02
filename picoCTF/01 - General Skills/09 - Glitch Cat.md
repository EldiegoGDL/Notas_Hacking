## Descripción

Our flag printing service has started glitching!

Additional details will be available after launching your challenge instance.

## Solución

```
DiegoGDL-picoctf@webshell:~$ nc saturn.picoctf.net 55026 | grep "picoCTF"
'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
````

luego de tener la llave glicheada procedemos a traducir las secuencuas chr(????) a ASCII

picoCTF{gl17ch_m3_n07_a4392d2e}
## Referencias

la pagina prara traducir ascii
[Hex to String | Hex to ASCII Converter](https://www.rapidtables.com/convert/number/hex-to-ascii.html?utm_source=chatgpt.com)

y la coneccion netcat



