# Obedient Cat

## Objetivo
This file has a flag in plain sight (aka "in-the-clear").

## Solucion
```bash
┌──(kali㉿kali)-[~/hacking]
└─$ wget https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag
--2022-09-25 13:32:57--  https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: ‘flag.1’

flag.1               100%[=====================>]      34  --.-KB/s    in 0s

2022-09-25 13:32:59 (12.1 MB/s) - ‘flag.1’ saved [34/34]


┌──(kali㉿kali)-[~/hacking]
└─$ ls
'CuestionarioCiberseguridad(Tema 2).pdf'   file   flag.1          strings
'Cuestionario(Tema 3) (1).pdf'             flag   notas_hacking

┌──(kali㉿kali)-[~/hacking]
└─$ cat flag
picoCTF{s4n1ty_v3r1f13d_f28ac910}

┌──(kali㉿kali)-[~/hacking]
└─$ 

```
picoCTF{s4n1ty_v3r1f13d_f28ac910}

## Notas adicionales

## Referencias