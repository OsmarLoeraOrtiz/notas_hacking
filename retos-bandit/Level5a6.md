# Bandit Level6

## Objetivo
The password for the next level is stored **somewhere on the server** and has all of the following properties:

-   owned by user bandit7
-   owned by group bandit6
-   33 bytes in size

## Datos de acceso
bandit5
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

## Solucion
```
bandit5@bandit:~$ find -type f -size 1033c
./inhere/maybehere07/.file2
bandit5@bandit:~$ cd inhere/maybehere07
bandit5@bandit:~/inhere/maybehere07$ cat ./.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        bandit5@bandit:~/inhere/maybehere07$ 

```
## Notas adicionales

## Referencias