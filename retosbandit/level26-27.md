# Level 27

## Objetivo
Good job getting a shell! Now hurry and grab the password for bandit27!

## Datos de acceso al nivel
User: bandit25
Password: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
Host: bandit.labs.overthewire.org  
Port: 2220

Realizar los pasos anteriores para entrar a la terminal del usuario bandit26.

## Solución
```
bandit26@bandit:~$ ls
bandit27-do  text.txt
bandit26@bandit:~$ file bandit27-do
bandit27-do: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=037b97b430734c79085a8720c90070e346ca378e, for GNU/Linux 3.2.0, not stripped
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
bandit26@bandit:~$
```
## Notas adicionales
* 
## Referencias