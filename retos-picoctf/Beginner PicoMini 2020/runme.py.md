# runme.py
## Objetivo
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/86/runme.py)
## Solucion
```bash
┌──(kali㉿kali)-[~/hacking]
└─$ cat runme.py
#!/usr/bin/python3
################################################################################
# Python script which just prints the flag
################################################################################

flag ='picoCTF{run_s4n1ty_run}'
print(flag)


┌──(kali㉿kali)-[~/hacking]
└─$ python runme.py
picoCTF{run_s4n1ty_run}

```

## Notas adicionales

## Referencias