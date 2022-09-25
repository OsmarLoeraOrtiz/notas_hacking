# Based

## Objetivo
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.

## Solucion
```bash
┌──(kali㉿kali)-[~/hacking]
└─$ nc jupiter.challenges.picoctf.org 29956
Let us see how data is stored
pie
Please give the 01110000 01101001 01100101 as a word.
...
you have 45 seconds.....

Input:
pie
Please give me the  157 166 145 156 as a word.
Input:
oven
Please give me the 636f6d7075746572 as a word.
Input:
computer
You haveve beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}

┌──(kali㉿kali)-[~/hacking]
└─$  
_______________________________________________________


C:\Users\Osmar>python3
>>> 
>>> import sys
>>> def convert(x,base):
...     for elem in x.split(" "):
...           sys.stdout.write(chr(int(elem,base)))
...


```
picoCTF{learning_about_converting_values_b375bb16}
## Notas adicionales

## Referencias