# How can I retrieve the message

## Objetivos
Consider an RSA that is using twin primes. IF=10403 and e=8743. Show how the adversary can recover the message corresponding to c=99


## Solución 
```bash
┌──(kali㉿kali)-[/opt/RsaCtfTool]
└─$ python3 RsaCtfTool.py -n 10403 -e 8743 --uncipher 99
private argument is not set, the private key will not be displayed, even if recovered.

[*] Testing key /tmp/tmpo59ttz3z.
attack initialized...
[*] Performing smallq attack on /tmp/tmpo59ttz3z.
[*] Attack success with smallq method !

Results for /tmp/tmpo59ttz3z:

Unciphered data :
HEX : 0x2496
INT (big endian) : 9366
INT (little endian) : 38436
utf-16 : 阤
STR : b'$\x96'
HEX : 0x2496
INT (big endian) : 9366
INT (little endian) : 38436
utf-16 : 阤
STR : b'$\x96'

respuesta es 9366
```

## Notas adicionales 