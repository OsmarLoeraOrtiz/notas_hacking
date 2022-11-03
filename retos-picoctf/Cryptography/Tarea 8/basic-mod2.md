## Objetivo
A new modular challenge! Download the message [here](https://artifacts.picoctf.net/c/499/message.txt). Take each number mod 41 and find the modular inverse for the result. Then map to the following character set: 1-26 are the alphabet, 27-36 are the decimal digits, and 37 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
## Solucion
```bash
datos = open("message.txt").read().split()
flag=""
for n in datos:
        c = pow(int(n), -1, 41)
        if c>=1 and c<=26:
                s = chr(c+64)
        elif c>=27 and c<=36:
                s = chr(c+21)
        else:
                s = "_"
        flag += s

print(flag)

┌──(kali㉿kali)-[~/Downloads]
└─$ python3 explo.py
1NV3R53LY_H4RD_C680BDC1

```
picoCTF{1NV3R53LY_H4RD_C680BDC1}
## Notas adicionales
![[Pasted image 20221030201229.png]]
## Referencias