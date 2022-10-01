# JaWT Scratchpad

## Objetivo
AUTHOR: JOHN HAMMOND

Internal server errors can be intentionally returned by this challenge. If you experience one, try clearing your cookies.

#### Description

Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864

## Solucion
```bash
#Copiamos la cookie
┌──(kali㉿kali)-[~]
└─$ nano hash

┌──(kali㉿kali)-[~]
┌──(kali㉿kali)-[~]
└─$ cat hash                                                                       eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiY2FybG9zIn0.ibA8ZjnNXLYfuOIQWln6-CmmzUhw-bsu3BivkwnNYDk
┌──(kali㉿kali)-[~]
└─$ john hash -w=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)
1g 0:00:00:04 DONE (2022-10-01 15:23) 0.2293g/s 1696Kp/s 1696Kc/s 1696KC/s iloverob4live345..ilovemymother@
Use the "--show" option to display all of the cracked passwords reliably
Session completed.

┌──(kali㉿kali)-[~]
└─$    

#Editamos la cookie en la pagina jwt.io
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s
#Cambiamos y guardamos la cookie en el navegador
picoCTF{jawt_was_jus_what_you_thought_f859ab2f}

```
## Notas adicionales

## Referencias
https://jwt.io/