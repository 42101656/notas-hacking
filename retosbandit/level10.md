# Level 10

## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de acceso al nivel
User: bandit9
Password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit9@bandit:~$ ls -lah
total 40K
drwxr-xr-x  2 root     root    4.0K Oct  5 06:19 .
drwxr-xr-x 70 root     root    4.0K Oct  5 06:20 ..
-rw-r--r--  1 root     root     220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root    3.7K Jan  6  2022 .bashrc
-rw-r-----  1 bandit10 bandit9  19K Oct  5 06:19 data.txt
-rw-r--r--  1 root     root     807 Jan  6  2022 .profile
bandit9@bandit:~$ file data.txt
data.txt: data
bandit9@bandit:~$ strings data.txt | grep ==
x]T========== theG)"
========== passwordk^
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$
```
## Notas adicionales
* El comando strings funciona para extraer cadenas de texto entendibles de un archivo binario.
## Referencias
https://www.howtogeek.com/427805/how-to-use-the-strings-command-on-linux/