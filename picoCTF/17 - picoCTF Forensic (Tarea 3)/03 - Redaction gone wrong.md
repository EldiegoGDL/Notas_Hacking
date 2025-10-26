## Descripción
Now you DON’T see me.
This report has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?
## Solución
```
sudo apt install pdftotext 
┌──(diego㉿Maquina-deGuerra)-[~/Documentos/forensic/Redactiongonewrong]
└─$ cat Financial_Report_for_ABC_Labs.txt 

Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.
Breakdown - Just painted over in MS word.

Cost Benefit Analysis
Credit Debit
This is not the flag, keep looking
Expenses from the
picoCTF{C4n_Y0u_S33_m3_fully}
Redacted document.

```
## Notas adicionales
+ con wget descargamos el reporte
+ y con file revisamos que tipo de documento es 
+ al ver que es un pdf
+ descargamos un nuevo paquete llamado pdftotext que como su nombre indica convierte pdf a archivos de texto .txt
+ al hacerlo .txt lo abrimos y este ya es legible y contiene la bandera
## Referencias
