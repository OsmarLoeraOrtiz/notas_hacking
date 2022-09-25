# Bandit Level13

## Objetivo
The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on

## Datos de acceso
bandit13
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

## Solucion
```bash
Osmar@LAPTOP-HGLRK1OL MINGW64 ~
$ ssh -i llave14 bandit14@bandit.labs.overthewire.org -p 2220
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
bandit14@bandit:~$


```

## Notas adicionales
The private key is kept on the computer you log in from, while the public key is stored on the **.ssh/authorized_keys**.

Formato de las llaves publicas:
```
<ssh-rsa or ssh-dss> <really long string of nonsense> <username>@<host
```

To create your public and private SSH keys on the command-line:
```
mkdir ~/.ssh
chmod 700 ~/.ssh
ssh-keygen -t rsa
```

## Referencias
https://help.ubuntu.com/community/SSH/OpenSSH/Keys