## Objetivo
Can you get the flag? Run this [Python program](https://artifacts.picoctf.net/c/428/bloat.flag.py) in the same directory as this [encrypted flag](https://artifacts.picoctf.net/c/428/flag.txt.enc).
## Solucion
```bash
imprimimos el script y en la funcion arg133 identificamos que se verifica si es la bandera, si no es la bandera te manda un msj y se acaba la ejecucion. Solo hay que quitar la linea que cancela la ejecucion:
def arg133(arg432):

  if arg432 == a[71]+a[64]+a[79]+a[79]+a[88]+a[66]+a[71]+a[64]+a[77]+a[66]+a[68]:

    return True

  else:

    print(a[51]+a[71]+a[64]+a[83]+a[94]+a[79]+a[64]+a[82]+a[82]+a[86]+a[78]+\

        a[81]+a[67]+a[94]+a[72]+a[82]+a[94]+a[72]+a[77]+a[66]+a[78]+a[81]+\

        a[81]+a[68]+a[66]+a[83])
	sys.exit(0) <== ESTA LINEA
    return False

y nos da:
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 exp2.py
Please enter correct password for flag: r
That password is incorrect
Welcome back... your flag, user:
picoCTF{d30bfu5c4710n_f7w_b8062eec}

```

## Notas adicionales

## Referencias