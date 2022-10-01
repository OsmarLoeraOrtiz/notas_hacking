# Static ain't always noise
## Objetivo
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static)? This [BASH script](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh) might help!

## Solucion
```bash
┌──(kali㉿kali)-[~/hacking]
└─$ strings static | grep pico
picoCTF{d15a5m_t34s3r_98d35619}

```
## Notas adicionales
***strings***: muestra los caracteres imprimibles
## Referencias