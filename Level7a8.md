# Bandit Level7

## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**

## Datos de acceso
bandit7
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

## Solucion
```
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ grep data.txt "millionth"
grep: millionth: No such file or directory
bandit7@bandit:~$ grep 'millionth' data.txt
millionth       cvX2JJa4CFALtqS87jk27qwqGhBM9plV
bandit7@bandit:~$ 

```
## Notas adicionales

## Referencias