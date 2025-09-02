
## Descripción

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Solución
Para encontrar la flag utilicé el comando `Select-String` en PowerShell, indicando la ruta del archivo y el patrón de búsqueda `"flag|picoCTF"`. El comando fue `Select-String -Path "C:\Users\diego\OneDrive\Escritorio\temp\file" -Pattern "flag|picoCTF"`.

![[Pasted image 20250830140343.png]]
picoCTF{grep_is_good_to_find_things_dba08a45}
## Referencias

Select-String -Path "C:\Ruta\Al\Archivo\X" -Pattern "X|X"
