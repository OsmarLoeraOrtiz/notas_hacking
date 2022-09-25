# Glitch Cat
## Objetivo

## Solucion
```bash
┌──(kali㉿kali)-[~/hacking]
└─$ nc saturn.picoctf.net 65353
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'

┌──(kali㉿kali)-[~/hacking]
└─$ python
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> letras = [chr(0x39), chr(0x63), chr(0x34) , chr(0x32), chr(0x61), chr(0x34) ,ch
r(0x35),chr(0x64)]
>>> flag = ""
>>> for x in letras:
...     flag += x
...
>>> print(flag)
9c42a45d
>>>

```
picoCTF{gl17ch_m3_n07_9c42a45d}
## Notas adicionales

## Referencias