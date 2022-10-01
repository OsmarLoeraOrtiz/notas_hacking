# Wave a flag
## Objetivo
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm) has extraordinarily helpful information.

## Solucion
```bash
┌──(kali㉿kali)-[~/hacking]
└─$ chmod +x warm

┌──(kali㉿kali)-[~/hacking]
└─$ ./warm
Hello user! Pass me a -h to learn what I can do!

┌──(kali㉿kali)-[~/hacking]
└─$ ./warm -h
Oh, help? I actually dont do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_d6969390}

┌──(kali㉿kali)-[~/hacking]
└─$ 
picoCTF{b1scu1ts_4nd_gr4vy_d6969390}

```
## Notas adicionales

## Referencias