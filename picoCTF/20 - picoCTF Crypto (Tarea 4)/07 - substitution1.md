## Descripción
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again.Download the message [here](https://artifacts.picoctf.net/c/182/message.txt).
## Solución
| A   | B   | C   | D   | E   | F   | G   | H   | I   | J   | K   | L   | M   | N   | O   | P   | Q   | R   | S   | T   | U   | V   | W   | X   | Y   | Z   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| J   |     | S   |     | R   | T   | M   | A   | Z   |     |     | H   |     |     | K   | B   |     |     | E   | Y   |     |     |     |     |     |     |
t  h  e       f   l   a   g      i s 
y  a  r       t   h   j   m       z e

```python
from string import ascii_uppercase, ascii_lowercase

  

alphabet = 'jlsqrtmaz-vhxckbudeynwg-o-'

#           ABCDEFGHIJKLMNOPQRSTUVWXYZ

#           jlsqrtmaz-vhxckbudeynwg-o- 

text = '''

SYTe (eakdy tkd sjbyndr yar thjm) jdr j yobr kt skxbnyrd ersndzyo skxbryzyzkc. Skcyreyjcye jdr bdrercyrq gzya j ery kt sajhhrcmre gazsa yrey yarzd sdrjyzwzyo, yrsaczsjh (jcq mkkmhzcm) evzhhe, jcq bdklhrx-ekhwzcm jlzhzyo. Sajhhrcmre nenjhho skwrd j cnxlrd kt sjyrmkdzre, jcq garc ekhwrq, rjsa ozrhqe j eydzcm (sjhhrq j thjm) gazsa ze enlxzyyrq yk jc kchzcr eskdzcm erdwzsr. SYTe jdr j mdrjy gjo yk hrjdc j gzqr jddjo kt skxbnyrd ersndzyo evzhhe zc j ejtr, hrmjh rcwzdkcxrcy, jcq jdr akeyrq jcq bhjorq lo xjco ersndzyo mdknbe jdkncq yar gkdhq tkd tnc jcq bdjsyzsr. Tkd yaze bdklhrx, yar thjm ze: bzskSYT{TD3UN3CSO_4774SV5_4D3_S001_7JJ384LS}

'''.lower()

  

# we start lowercase, and make capital letters for ones we know

  

dec = ''

  

for c in text:

    if c in alphabet:

        dec += ascii_uppercase[alphabet.index(c)]    # if we know the transposition, good

    else:

        dec += c

  

print(dec)

```

CTFS (SHORT FOR CAPTURE THE FLAG) ARE A TYPE OF COMPUTER SECURITY COMPETITION. CONTESTANTS ARE PRESENTED WITH A SET OF CHALLENGES WHICH TEST THEIR CREATIVITY, TECHNICAL (AND GOOGLING) SKILLS, AND PROBLEMJSOLVING ABILITY. CHALLENGES USUALLY COVER A NUMBER OF CATEGORIES, AND WHEN SOLVED, EACH YIELDS A STRING (CALLED A FLAG) WHICH IS SUBMITTED TO AN ONLINE SCORING SERVICE. CTFS ARE A GREAT WAY TO LEARN A WIDE ARRAY OF COMPUTER SECURITY SKILLS IN A SAFE, LEGAL ENVIRONMENT, AND ARE HOSTED AND PLAYED BY MANY SECURITY GROUPS AROUND THE WORLD FOR FUN AND PRACTICE. FOR THIS PROBLEM, THE FLAG IS: 

PICOCTF{FR3QU3NCY_4774CK5_4R3_C001_7AA384BC}
## Notas adicionales
+ con wget descargamos el mensaje
+ teniendo en cuenta la descripción nos dirigimos al navegador para usar una pagina que usara como abecedario
+ pero como no tenemos la llave la buscaremos sabiendo unicamente que una parte siempre sera la misma
+ el formato picoCTF{XXXX-XXXX-XXXX-}
+ con eso en cuenta usamos un codigo y vamos descartando poco a poco
+ hasta dar con la bandera
## Referencias
