## Objetivo
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled2.png)
## Solucion
```bash
Ejecutamos stegsolve.jar y hacemos una combinacion de las dos imagenes:
┌──(kali㉿kali)-[/opt]
└─$ java -jar /opt/stegsolve.jar
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

y al combinar:
picoCTF{7188864c}

```

## Notas adicionales
![[Pasted image 20221030201229.png]]
## Referencias