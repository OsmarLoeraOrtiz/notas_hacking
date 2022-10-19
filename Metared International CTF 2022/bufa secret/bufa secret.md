# Metared International CTF 2022

## Descripcion

Juan the explororer extracted this file from the site on the last expedition, but it appears to have been **corrupted**. This may be the secret code to open Francisco Villa vault that was found inside the "Cerro de la Bufa" in Zacatecas City. Can you identify what it once was and possibly fix it ? .

On June 23, 1914, this place was the scene of the "La toma de Zacatecas" (1914), where the revolutionary troops of General Francisco Villa defeated the Huertista army, defining the destiny of the nation.

## Pistas (Si hay)



## Solución

``` Bash

Abrimos el archivo como hexeditor y colocamos el contenido en hexadecimal para poder poner los caracteres como PNG y IHDR, al hacerlo podemos abrir la imagen

┌──(kali㉿kali)-[~/Metared International CTF 2022/bufa secret]
└─$ hexeditor corrupted.dta 
                                                                                                                   
┌──(kali㉿kali)-[~/Metared International CTF 2022/bufa secret]
└─$ open corrupted.dta 
                                                                                                                   
┌──(kali㉿kali)-[~/Metared International CTF 2022/bufa secret]


```

## Referencias

https://en.wikipedia.org/wiki/Portable_Network_Graphics