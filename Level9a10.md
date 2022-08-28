# Bandit Level9a10

## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de acceso
bandit9
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

## Solucion
```
bandit9@bandit:~$ cat data.txt | strings | grep ==
========== the*2i"4
========== password
Z)========== is
&========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
bandit9@bandit:~$ 

```
## Notas adicionales

## Referencias