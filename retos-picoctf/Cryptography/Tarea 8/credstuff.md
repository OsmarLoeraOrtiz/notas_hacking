## Objetivo
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it? Download the leak [here](https://artifacts.picoctf.net/c/534/leak.tar). The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.

## Solucion
```bash
passw = open("passwords.txt").read().split()
user = open("usernames.txt").read().split()

for i in range(len(passw)):
        print(passw[i],user[i])

┌──(kali㉿kali)-[~/Downloads/leak]
└─$ python3 pass.py | grep cultiris
cvpbPGS{P7e1S_54I35_71Z3} cultiris

Aplicamos ROT13:
picoCTF{C7r1F_54V35_71M3}




```

## Notas adicionales
![[Pasted image 20221030201229.png]]
## Referencias