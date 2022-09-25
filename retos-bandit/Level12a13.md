# Bandit Level12

## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Datos de acceso
bandit12
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

## Solucion
```bash
bandit12@bandit:~$ mkdir /tmp/lalonganiza
bandit12@bandit:~$ cd /tmp/lalonganiza
bandit12@bandit:/tmp/lalonganiza$ xxd -r data.txt data.txt
xxd: data.txt: No such file or directory
bandit12@bandit:/tmp/lalonganiza$ xxd -r ~/data.txt data.txt
bandit12@bandit:/tmp/lalonganiza$ file data.txt
data.txt: gzip compressed data, was "data2.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/lalonganiza$ mv data.txt data.gz
bandit12@bandit:/tmp/lalonganiza$ ls
data.gz
bandit12@bandit:/tmp/lalonganiza$ gzip data.gz
gzip: data.gz already has .gz suffix -- unchanged
bandit12@bandit:/tmp/lalonganiza$ man gzip
bandit12@bandit:/tmp/lalonganiza$ gzip -d  data.gz
bandit12@bandit:/tmp/lalonganiza$ ls
data
bandit12@bandit:/tmp/lalonganiza$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/lalonganiza$ mv data data.bz2
bandit12@bandit:/tmp/lalonganiza$ ls
data.bz2
bandit12@bandit:/tmp/lalonganiza$ bzip2 -d data.bz2
bandit12@bandit:/tmp/lalonganiza$ ls
data
bandit12@bandit:/tmp/lalonganiza$ file data
data: gzip compressed data, was "data4.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/lalonganiza$ mv data data.gz
bandit12@bandit:/tmp/lalonganiza$ ls
data.gz
bandit12@bandit:/tmp/lalonganiza$ gzip -d data.gz
bandit12@bandit:/tmp/lalonganiza$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/lalonganiza$ mv data data.tar
bandit12@bandit:/tmp/lalonganiza$ tar xf data.tar
bandit12@bandit:/tmp/lalonganiza$ file data
data: cannot open `data` (No such file or directory)
bandit12@bandit:/tmp/lalonganiza$ ls
data5.bin  data.tar
bandit12@bandit:/tmp/lalonganiza$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/lalonganiza$ mv data5.bin data5.tar
bandit12@bandit:/tmp/lalonganiza$ tar xf data5.tar
bandit12@bandit:/tmp/lalonganiza$ ls
data5.tar  data6.bin  data.tar
bandit12@bandit:/tmp/lalonganiza$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/lalonganiza$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/lalonganiza$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/lalonganiza$ ls
data5.tar  data6  data.tar
bandit12@bandit:/tmp/lalonganiza$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/lalonganiza$ mv data6 data6.tar
bandit12@bandit:/tmp/lalonganiza$ tar xf data6.tar
bandit12@bandit:/tmp/lalonganiza$ ls
data5.tar  data6.tar  data8.bin  data.tar
bandit12@bandit:/tmp/lalonganiza$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/lalonganiza$ mv data8.bin data8.gzip
bandit12@bandit:/tmp/lalonganiza$ gzip -d data8.gzip
gzip: data8.gzip: unknown suffix -- ignored
bandit12@bandit:/tmp/lalonganiza$ ls
data5.tar  data6.tar  data8.gzip  data.tar
bandit12@bandit:/tmp/lalonganiza$ gzip -d data8.gz
gzip: data8.gz: No such file or directory
bandit12@bandit:/tmp/lalonganiza$ mv data8.gzip data8.gz
bandit12@bandit:/tmp/lalonganiza$ gzip -d data8.gz
bandit12@bandit:/tmp/lalonganiza$ ls
data5.tar  data6.tar  data8  data.tar
bandit12@bandit:/tmp/lalonganiza$ file data8
data8: ASCII text
bandit12@bandit:/tmp/lalonganiza$ cat data8
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:/tmp/lalonganiza$

```
## Notas adicionales
![[Pasted image 20220829201932.png]]

## Referencias
https://www.youtube.com/watch?v=1UhQlvQy-qk&t=890s