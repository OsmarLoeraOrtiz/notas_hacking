# Bandit Level9a10

## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de acceso
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Solucion
```
bandit9@bandit:~$ cat data.txt | strings | grep ==
========== the*2i"4
========== password
Z)========== is
&========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$ 

```
## Notas adicionales

## Referencias