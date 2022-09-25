# PW Crack 1
## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/53/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/53/level1.flag.txt.enc) in the same directory too.

## Solucion
```bash
┌──(kali㉿kali)-[~/hacking]
└─$ cat level1.py
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "8713"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()

┌──(kali㉿kali)-[~/hacking]
└─$ python
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> def str_xor(secret, key):
...     #extend key to secret length
...     new_key = key
...     i = 0
...     while len(new_key) < len(secret):
...         new_key = new_key + key[i]
...         i = (i + 1) % len(key)
...     return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
...
>>> flag_enc = open('level1.flag.txt.enc', 'rb').read()
>>> decryption = str_xor(flag_enc.decode(), user_pw)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
 NameError: name 'user_pw' is not defined
>>> decryption = str_xor(flag_enc.decode(), "8713")
>>> print(decryption)
picoCTF{545h_r1ng1ng_1b2fd683}
>>

```
picoCTF{545h_r1ng1ng_1b2fd683}
## Notas adicionales

## Referencias