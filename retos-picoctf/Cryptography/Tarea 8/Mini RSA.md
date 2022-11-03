## Objetivo
What happens if you have a small exponent? There is a twist though, we padded the plaintext so that (M ** e) is just barely larger than N. Let's decrypt this: [ciphertext](https://mercury.picoctf.net/static/a9d46a88f2602fa48edf086a5afbfed8/ciphertext)

## Solucion
```bash
>>> for i in range(10000):
...     m, is_true_root = gmpy2.iroot(i*n + c, e)
...     if is_true_root:
...         print(f"Found i = {i}")
...         print("Message: {}".format(bytearray.fromhex(format(m, 'x')).decode()))
...         break
... 
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 exp1.py
Found i = 3533
Message:                                                                                                         picoCTF{e_sh0u1d_b3_lArg3r_aef7377d}

>>> 

```

## Notas adicionales
![[Pasted image 20221030201229.png]]
## Referencias