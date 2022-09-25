# Bandit Level20

## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think

## Datos de acceso
bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Solucion
```bash
bandit20@bandit:~$ nc -l 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 3827234
bandit20@bandit:~$ jobs
[1]+  Running                 nc -l 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
bandit20@bandit:~$ ./suconnect 3030
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+  Done                    nc -l 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ 

```
## Notas adicionales

## Referencias