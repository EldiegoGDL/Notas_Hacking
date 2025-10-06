## Descripción
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.
## Solución
con wget descargamos el archivo mystery para luego usar file para ver que tipo de archivo es
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/c0rrupt]
└─$ file mystery                                                            
mystery: data

```
usamos un xxd para ver sus bites
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/c0rrupt]
└─$ xxd -l 100 mystery
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71                                .d.q

```
y nos damos cuenta que es un png corrupto y lo corregimos con hexeditor
![[Pasted image 20251006111409.png]]
despues instalaremos el paquete pngcheck para analisar que falla
```
sudo apt install pngcheck
```
al ver que un bloque esta corrupto
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/c0rrupt]
└─$ pngcheck -v mystery
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in mystery

```

tambien corregimos pHYs
![[Pasted image 20251006144500.png]]
y corrgimos la longitud de los bites
![[Pasted image 20251006145607.png]]
y corregimos el tamaño
![[Pasted image 20251006150731.png]]
y volvemos a hacer un file
```
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/c0rrupt]
└─$ file  mystery         
mystery: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced

```
y como ya se reconose como png lo abrimos y es una imagen con la bandera


picoCTF{c0rruptt10n_1847995}
## Referencias
pngcheck -->un paquete de kalilinux