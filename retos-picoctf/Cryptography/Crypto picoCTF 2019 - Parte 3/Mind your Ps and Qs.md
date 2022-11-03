## Objetivo
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values)
## Solucion
```bash
Lo pasamos por la pagina Factordb(La n es muy chica y se puede factorizar) y obtenemos:
p = 2159947535959146091116171018558446546179
q = 658558036833541874645521278345168572231473

Despues calculamos totient n(tn), llave privada(d) y al final lo desencriptamos(m):
┌──(kali㉿kali)-[~]
└─$ python3                
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> c = 843044897663847841476319711639772861390329326681532977209935413827620909782846667
>>> n = 1422450808944701344261903748621562998784243662042303391362692043823716783771691667
>>> e = 65537
>>> 
>>> p = 2159947535959146091116171018558446546179
>>> q = 658558036833541874645521278345168572231473
>>> 
>>> tn = (p-1)*(q-1)
>>> from Crypto.Util.number import inverse
>>> from Crypto.Util.number import long_to_bytes
>>> d = inverse(e, tn)
>>> m = pow(c,d,n)
>>> m
13016382529449106065927291425342535437996222135352905256639555294957886055592061
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_00264570}'
>>> 

```
picoCTF{sma11_N_n0_g0od_00264570}
## Notas adicionales
![[Pasted image 20221030201229.png]]
## Referencias
http://factordb.com/index.php?query=1422450808944701344261903748621562998784243662042303391362692043823716783771691667