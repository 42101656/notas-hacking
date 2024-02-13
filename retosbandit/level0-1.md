# Level 1

## Objetivo
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

## Datos de acceso al nivel
User: bandit0
Password: bandit0
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit0@bandit:~$ ls -ll
total 4
-rw-r----- 1 bandit1 bandit0 33 Oct  5 06:19 readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```
## Notas adicionales

## Referencias