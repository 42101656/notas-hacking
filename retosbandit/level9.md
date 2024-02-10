# Level 9

## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once.

## Datos de acceso al nivel
User: bandit8
Password: TESKZC0XvTetK0S9xNwm25STk5iWrBvP
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit8@bandit:~$ ls -lah
total 56K
drwxr-xr-x  2 root    root    4.0K Oct  5 06:19 .
drwxr-xr-x 70 root    root    4.0K Oct  5 06:20 ..
-rw-r--r--  1 root    root     220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root    root    3.7K Jan  6  2022 .bashrc
-rw-r-----  1 bandit9 bandit8  33K Oct  5 06:19 data.txt
-rw-r--r--  1 root    root     807 Jan  6  2022 .profile
bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$
```
## Notas adicionales
* El comando sort sirve para ordenar.
* La opción u del comando uniq  imprime las líneas únicas, es decir, no duplicadas.
## Referencias
https://h4ckseed.wordpress.com/2020/11/22/procesando-listas-en-linux-con-uniq/