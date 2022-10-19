# Metared International CTF 2022

## Descripcion

I downloaded one of my friend's files that describe how **frequently** he visits the "eden mine" in Zacatecas, México, but i think there might be more to it.

The most important time of the "eden mine" was during the XVII and XVIII centuries when production was mainly based in silver and gold. Given the floods in its shafts and how close it is to the city, in 1960 the exploitation of the mine ended, a little after it was adapted for tourism, being the most visited mine in the country by national and foreign tourists.

## Pistas (Si hay)



## Solución

``` Bash

from collections import Counter

text = "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"

letters = Counter(text)
print(len(letters))
print(letters)


┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/eden_mine]
└─$ nano ex.py                            
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/eden_mine]
└─$ python3 ex.py 
29
Counter({'C': 125, 'g': 123, 'l': 118, 's': 117, 'y': 115, 'p': 114, 'r': 113, 'u': 110, 'b': 108, 'w': 105, 'd': 103, 'a': 102, 'o': 102, 'x': 101, 'v': 99, 'c': 97, 'i': 95, 'n': 95, 'z': 95, 'f': 88, 'A': 88, 'e': 77, 'h': 73, 'B': 68, 'm': 51, 'q': 51, 't': 51, 'j': 49, 'k': 48})
                                                                           
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/eden_mine]
└─$ 

Realizamos un codigo en python que haga el analisis/conteo de letras que nos da, que es lo siguiente:

102 108 97 103 77 88 123 73 95 49 48 118 51 95 102 114 51 113 117 51 110 99 105 101 115 95 88 68 125

Esto lo pasamos de ascii a texto y obtenemos como resultado la bandera:
flagMX{I_10v3_fr3qu3ncies_XD}

```

## Referencias