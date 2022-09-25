# Bandit Level10

## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

## Datos de acceso
bandit10
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Solucion
``` bash
bandit10@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 May  7  2020 .
drwxr-xr-x 41 root     root     4096 May  7  2020 ..
-rw-r--r--  1 root     root      220 May 15  2017 .bash_logout
-rw-r--r--  1 root     root     3526 May 15  2017 .bashrc
-rw-r-----  1 bandit11 bandit10   69 May  7  2020 data.txt
-rw-r--r--  1 root     root      675 May 15  2017 .profile
bandit10@bandit:~$ base64 --decode data.txt > data2.txt
-bash: data2.txt: Permission denied
bandit10@bandit:~$ base64 --decode data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$
```
## Notas adicionales

## Referencias
https://www.serverlab.ca/tutorials/linux/administration-linux/how-to-base64-encode-and-decode-from-command-line/#:~:text=To%20decode%20with%20base64%20you,back%20into%20its%20original%20form.&text=Provided%20your%20encoding%20was%20not,should%20be%20your%20original%20string.