# Bandit Level

## Objetivo
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

## Datos de acceso
bandit29
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

## Solucion
```bash
bandit29@bandit:/tmp/pta/repo$ ls
README.md
bandit29@bandit:/tmp/pta/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit29
- password: <no passwords in production!>

bandit29@bandit:/tmp/pta/repo$ git branch -a
* (HEAD detached at c27fff7)
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/pta/repo$ git checkout dev
Previous HEAD position was c27fff7 initial commit of README.md
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/pta/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit29@bandit:/tmp/pta/repo$

```
## Notas adicionales

## Referencias