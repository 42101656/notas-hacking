# Level 20

## Objetivo
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Datos de acceso al nivel
User: bandit19
Password: awhqfNnAbc1naukrpqDYcF95h7HoMTrC
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit19@bandit:~$ ls -lah
total 36K
drwxr-xr-x  2 root     root     4.0K Oct  5 06:19 .
drwxr-xr-x 70 root     root     4.0K Oct  5 06:20 ..
-rwsr-x---  1 bandit20 bandit19  15K Oct  5 06:19 bandit20-do
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3.7K Jan  6  2022 .bashrc
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit19@bandit:~$ file bandit20-do
bandit20-do: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=037b97b430734c79085a8720c90070e346ca378e, for GNU/Linux 3.2.0, not stripped
bandit19@bandit:~$ ./bandit20-do
Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit19@bandit:~$
```
## Notas adicionales

* Un archivo ejecutable de tipo setuid puede ejecutar con los permisos de un usuario ciertos comandos.
## Referencias
https://en.wikipedia.org/wiki/Setuid