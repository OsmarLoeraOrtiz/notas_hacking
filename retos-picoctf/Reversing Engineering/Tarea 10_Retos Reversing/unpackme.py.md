## Objetivo
Can you get the flag? Reverse engineer this [Python program](https://artifacts.picoctf.net/c/464/unpackme.flag.py).
## Solucion
```bash
import base64
from cryptography.fernet import Fernet

payload = b'gAAAAABiMD1Dt87s50caSunQlHoZqPOwtGNaQXexN-gjKwZeuLEN_-v6UcFJHVXOT4B6DcD1SB7cnd6yTcHg9e9LZCAeJY2cJ0r0sfyGPRiH60F-WbkyUjlAdDywI8RPdTpDYLuBmpZ_Kun-kHyTzMjeKR6R26Z4JITUS8n7Dj9X--9eNLajH6UuYD4GkjRACpsidl_8z33DlB86u_xDCMMm7HFK2oJTs8HG1fBex6enQsu0frUAJbx56DxhRvWawAysDMtLE50vaohrzkVV7Yaz4ClilwgfjQ=='

key_str = 'correctstaplecorrectstaplecorrec'
key_base64 = base64.b64encode(key_str.encode())
f = Fernet(key_base64)
plain = f.decrypt(payload)
exec(plain.decode())

Podemos ver que la carga útil es descifrada y luego ejecutada por `exec`, imprimamos la carga útil antes del `exec`comando agregando `print(plain.decode())`

┌──(kali㉿kali)-[~/Downloads]
└─$ python3 unpackme.flag.py

pw = input('What\'s the password? ')

if pw == 'batteryhorse':
  print('picoCTF{175_chr157m45_5274ff21}')
else:
  print('That password is incorrect.')


## Notas adicionales

## Referencias