# Level 4

## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.

## Datos de acceso al nivel
User: bandit3
Password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit3@bandit:~$ ls -la
total 24
drwxr-xr-x  3 root root 4096 Oct  5 06:19 .
drwxr-xr-x 70 root root 4096 Oct  5 06:20 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
drwxr-xr-x  2 root root 4096 Oct  5 06:19 inhere
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit3@bandit:~$ cat ~/inhere/.hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
bandit3@bandit:~$

```
## Notas adicionales
* La opcion -a en el comando ls sirve para mostrar los archivos ocultos.
## Referencias
https://www.geeksforgeeks.org/ls-command-in-linux/