## Objetivo
Can you get the flag? Run this [Python program](https://artifacts.picoctf.net/c/386/patchme.flag.py) in the same directory as this [encrypted flag](https://artifacts.picoctf.net/c/386/flag.txt.enc).
## Solucion
```bash
  
Imprimimos el script y obtenemos el codigo en la funcion level_1_pw_check es donde se verifica la bandera, solo hay que quitar donde se compara la bandera y lo indentamos como se debe y nos dara la bandera:
def level_1_pw_check():

    user_pw = input("Please enter correct password for flag: ")
**************************************************
    if( user_pw == "ak98" + \<==ESTA

                   "-=90" + \<==ESTA

                   "adfjhgj321" + \<==ESTA

                   "sleuth9000"): <==ESTA
***************************************************
        print("Welcome back... your flag, user:")

        decryption = str_xor(flag_enc.decode(), "utilitarian")

        print(decryption)

        return

    print("That password is incorrect")
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 exp2.py    
Please enter correct password for flag: d
Welcome back... your flag, user:
picoCTF{p47ch1ng_l1f3_h4ck_c4a4688b}

```

## Notas adicionales

## Referencias