## Objetivo
Can you get the flag? Download this [binary](https://artifacts.picoctf.net/c/115/gdbme). Here's the test drive instructions:

-   `$ chmod +x gdbme`
-   `$ gdb gdbme`
-   `(gdb) layout asm`
-   `(gdb) break *(main+99)`
-   `(gdb) run`
-   `(gdb) jump *(main+104)`
## Solucion
```bash
Sigues las instrucciones y te da la bandera:
	picoCTF{d3bugg3r_dr1v3_197c378a}

```

## Notas adicionales

## Referencias