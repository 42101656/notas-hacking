# Level 3

## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory.

## Datos de acceso al nivel
User: bandit2
Password: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit2@bandit:~$ ls -lh
total 4.0K
-rw-r----- 1 bandit3 bandit2 33 Oct  5 06:19 spaces in this filename
bandit2@bandit:~$ cat "spaces in this file"
cat: 'spaces in this file': No such file or directory
bandit2@bandit:~$ cat 'spaces in this file'
cat: 'spaces in this file': No such file or directory
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit1@bandit:~$
```
## Notas adicionales
* Las comillas sirven para indicar el nombre con espacios.
## Referencias