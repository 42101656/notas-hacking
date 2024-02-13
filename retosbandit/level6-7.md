# Level 7

## Objetivo
The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

## Datos de acceso al nivel
User: bandit6
Password: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit6@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Oct  5 06:19 .
drwxr-xr-x 70 root root 4096 Oct  5 06:20 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:~$
```
## Notas adicionales
* La opción -user bandit7 sirve para buscar los archivos que tengan como dueño al usuario bandit7.
* La opción -group bandit6 sirve para buscar los archivos que tengan como dueño al grupo bandit6.
* La opción 2>/dev/null redirecciona(>) la salida de errores(2) hacia el dispositivo nulo (/dev/null). En otras palabras, no se muestran los errores.
## Referencias
https://blog.desdelinux.net/que-es-devnull-y-como-puede-ayudarte/