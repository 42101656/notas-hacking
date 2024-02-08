# Level 2

## Objetivo
The password for the next level is stored in a file called **-** located in the home directory

## Datos de acceso al nivel
User: bandit1
Password: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit1@bandit:~$ ls -l
total 4
-rw-r----- 1 bandit2 bandit1 33 Oct  5 06:19 -
bandit1@bandit:~$ cat ~/-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
```
## Notas adicionales
* Recuerda que ~ indica el directorio home.*
## Referencias