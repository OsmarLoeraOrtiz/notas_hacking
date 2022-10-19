# Metared International CTF 2022

## Descripcion

I want to join to the Caxcan club, but they have the *weirdest passwords*! I've managed to intercept the program they use to authenticate the passwords, but I don't know how to figure it out. Can you figure out the password for me.

The Caxcan were a partly nomadic indigenous people of Mexico. Under their leader, Tenamaztle, the Caxcan were allied with the Zacatecos against the Spaniards during the Mixtón Rebellion in 1540-42.

## Pistas (Si hay)



## Solución

``` Bash

>>> def swoop():
...     cadena = "}zudidsbybwxaqaqehxbebimt`jks{XNidpk"
...     text = list(cadena)
...     for i in range(len(text)):
...             if text[i] not in '{}':
...                     text[i] = chr(ord(text[i]) - (i % 6))
...     return text
... 
>>> lista = swoop()
>>> 
>>> for elem in lista:
...     print(elem,end="")
... 
}ysae_saw_ssap_nacxac_eht_hho{XMgalf

Solo cambiamos el orden de la cadena
flagMx{ohh_the_caxcan_pass_was_easy}


flagMx{ohh_the_caxcan_pass_was_easy}

```

## Referencias