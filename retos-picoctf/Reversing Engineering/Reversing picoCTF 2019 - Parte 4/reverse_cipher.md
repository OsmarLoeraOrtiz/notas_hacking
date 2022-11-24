## Objetivo
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev_this). Can you reverse the flag.

## Solucion
```bash
Abrimos ghidra desde la terminal:
┌──(kali㉿kali)-[~/Downloads]
└─$ ghidra &
[1] 7399
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
[1]  + done       ghidra

Abrimos el archivo ejecutable en la interfaz de ghidra y decompilamos, lo que al analizar nos damos que cuenta que ignora los primeros 8 caracteres y despues si es impar le suma 5 y si es par le quita 2:
  for (i = 0; i < 8; i = i + 1) {
    rev = flag[i];
    fputc((int)rev,flagrev);
  }
  for (j = 8; (int)j < 0x17; j = j + 1) {
    if ((j & 1) == 0) {
      rev = flag[(int)j] + '\x05';
    }
    else {
      rev = flag[(int)j] + -2;
    }
    fputc((int)rev,flagrev);
  }

Hacemos un codigo en python aplicando lo mismo, pero a la inversa y tenemos:
cifrado = open('rev_this','r').read()
print(cifrado)

for i in range(8, len(cifrado) - 1):
    if i & 1 == 0:
	    flag = chr(ord(cifrado[i]) - 5)
    else
		flag = chr(ord(cifrado[i]) - 5)

print(flag)

Y al ejecutarlo obtenemos:
picoCTF{w1{1wq8/7376j.:}
r3v3rs312528e05


```
picoCTF{r3v3rs312528e05}
## Notas adicionales

## Referencias