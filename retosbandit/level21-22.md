# Level 22

## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

## Datos de acceso al nivel
User: bandit21
Password: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit21@bandit:~$ cd /etc/cron.d
bandit21@bandit:/etc/cron.d$ ls -lah
total 56K
drwxr-xr-x   2 root root 4.0K Oct  5 06:20 .
drwxr-xr-x 106 root root  12K Oct  5 06:20 ..
-rw-r--r--   1 root root   62 Oct  5 06:19 cronjob_bandit15_root
-rw-r--r--   1 root root   62 Oct  5 06:19 cronjob_bandit17_root
-rw-r--r--   1 root root  120 Oct  5 06:19 cronjob_bandit22
-rw-r--r--   1 root root  122 Oct  5 06:19 cronjob_bandit23
-rw-r--r--   1 root root  120 Oct  5 06:19 cronjob_bandit24
-rw-r--r--   1 root root   62 Oct  5 06:19 cronjob_bandit25_root
-rw-r--r--   1 root root  201 Jan  8  2022 e2scrub_all
-rwx------   1 root root   52 Oct  5 06:20 otw-tmp-dir
-rw-r--r--   1 root root  102 Mar 23  2022 .placeholder
-rw-r--r--   1 root root  396 Feb  2  2021 sysstat
bandit21@bandit:/etc/cron.d$ file cronjob_bandit22
cronjob_bandit22: ASCII text
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:/etc/cron.d$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
bandit21@bandit:/etc/cron.d$
```
## Notas adicionales

*  El comando cron sirve para automatizar tareas en un tiempo determinado.
## Referencias
https://www.geeksforgeeks.org/cron-command-in-linux-with-examples/