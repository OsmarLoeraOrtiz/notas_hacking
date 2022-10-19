# Metared International CTF 2022

## Descripcion

When a communication protocol is used that does not encrypt the information, it travels in plain text, putting the information at risk. Can you find the flag of this enchilada?

## Pistas (Si hay)



## Solución

``` Bash

┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF]
└─$ cd laEnchilada 
                                                                          
┌──(anitars㉿kali)-[~/hacking/hacking/picoCTF/laEnchilada]
└─$ wireshark enchiladaCTF.pcap 



Abrimos la captura de paquetes con wireshark, seguimos un paquete 'TCP', en el paquete 37, encontraremos la bandera en base64, utilizaremos un convertidor online para convertir la bandera de base64 a texto. 

bandera en base64: ZmxhZ01Ye0VuY2gxbGFkYVIwamF5VmVyZDN9Cg==

bandera final: flagMX{Ench1ladaR0jayVerd3}

```

## Referencias

https://www.base64decode.org/