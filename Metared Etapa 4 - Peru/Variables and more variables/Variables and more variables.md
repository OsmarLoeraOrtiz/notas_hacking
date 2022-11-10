# Variables and more variables

## Objetivos
Considere un sistema RSA con p=7, q= 11 and = e=13, encuentre el texto plano correspondiente a c=17. Encuentra el valor de m


## Solución 
```bash
┌──(kali㉿kali)-[/opt/RsaCtfTool]
└─$ python3                                             
Python 3.10.7 (main, Sep  8 2022, 14:34:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> c = 17
>>> p = 7
>>> q = 11
>>> e = 13
>>> n = p * q
>>> from Crypto.Util.number import inverse
>>> tn= ( p - 1)*(q - 1)
>>> d = inverse (e, tn)
>>> d
37
>>> m = pow(c,d,n)
>>> m
52

```

## Notas adicionales 