# Bandit Level11

## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Datos de acceso
bandit11
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solucion
```bash
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt | tr A-Z N-M
tr: range-endpoints of 'N-M' are in reverse collating sequence order
bandit11@bandit:~$ cat data.txt | tr A-M N-Z
Tur cnffjbeq vf 5Tr8Y4qetPRsPk8htqjhRX8XSP6x2RUh
bandit11@bandit:~$ cat data.txt | tr A-Mn-z N-Za-m
The caffjbed if 5Te8Y4degPRfPk8hgdjhRX8XSP6k2RUh
bandit11@bandit:~$ cat data.txt | tr A-MN-Zn-za-m N-ZA-Ma-mn-z
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$

```
## Notas adicionales
tr syntax:

tr [options] SET1 [SET2]

Reemplaza los caracteres establecidos en el SET1 por los del SET2
## Referencias
https://en.wikipedia.org/wiki/Rot13
https://phoenixnap.com/kb/linux-tr#:~:text=The%20tr%20command%20is%20a,characters%2C%20and%20basic%20text%20replacement.