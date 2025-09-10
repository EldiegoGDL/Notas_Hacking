## Descripción
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/2/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/2/codebook.txt)

## Solución
primero con el comando wget cargamos al sistema el archivo .py y lo ejecutamos al recibir un mensaje que no encontro el archivo codebook.txt usamos wget y cargamos el archivo al sistema y volvemos a ejecutar el archivo .py para que encuentre el documento .txt y nos de la flag

```
DiegoGDL-picoctf@webshell:~$ python3 code.py                               
Couldn't find codebook.txt. Did you download that file into the same directory as this script?
DiegoGDL-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/2/codebook.txt
DiegoGDL-picoctf@webshell:~$ python3 code.py
picoCTF{c0d3b00k_455157_7d102d7a}
```
## Referencias
wget --> para cargar documentos 
python3 ---> para ejecutar archivos .py