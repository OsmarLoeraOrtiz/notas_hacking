# Bandit Level

## Objetivo
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

## Datos de acceso
bandit30
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

## Solucion
```bash
bandit30@bandit:/tmp/LOL/repo$ ls
README.md
bandit30@bandit:/tmp/LOL/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/LOL/repo$ git log
commit a325f29e1cc26b0f0dc5f89b4348e389b408cc87 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:28 2022 +0000

    initial commit of README.md
bandit30@bandit:/tmp/LOL/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
bandit30@bandit:/tmp/LOL/repo$ git tag
secret
bandit30@bandit:/tmp/LOL/repo$ git checkout secret
fatal: reference is not a tree: secret
bandit30@bandit:/tmp/LOL/repo$ git tag secret
fatal: tag 'secret' already exists
bandit30@bandit:/tmp/LOL/repo$ git show
commit a325f29e1cc26b0f0dc5f89b4348e389b408cc87 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:28 2022 +0000

    initial commit of README.md

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..029ba42
--- /dev/null
+++ b/README.md
@@ -0,0 +1 @@
+just an epmty file... muahaha
bandit30@bandit:/tmp/LOL/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/LOL/repo$ 

```
## Notas adicionales

## Referencias