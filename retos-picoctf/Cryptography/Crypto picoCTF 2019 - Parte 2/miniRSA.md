## Objetivo
Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/eb5e6df8e14c52873cf88c582a1a4008/ciphertext)? Something seems a bit small.
## Solucion
```bash
                                                                                                                    
┌──(kali㉿kali)-[~]
└─$ python3
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from gmpy2 import *
>>> from Crypto.Util.number import long_to_byte
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ImportError: cannot import name 'long_to_byte' from 'Crypto.Util.number' (/usr/local/lib/python3.10/dist-packages/Crypto/Util/number.py)
>>> from Crypto.Util.number import long_to_bytes
>>> gmpy2.get_context().precision = 2048
>>> e = 3
>>> c = 2205316413931134031074603746928247799030155221252519872650080519263755075355825243327515211479747536697517688468095325517209911688684309894900992899707504087647575997847717180766377832435022794675332132906451858990782325436498952049751141
>>> root, exact = iroot(c,e)
>>> long_to_bytes(root)
b'picoCTF{n33d_a_lArg3r_e_d0cd6eae}'
>>> 


```

## Notas adicionales
![[Pasted image 20221030201229.png]]
## Referencias