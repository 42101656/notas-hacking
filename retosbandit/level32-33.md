# Level 33

## Objetivo
After all this `git` stuff its time for another escape. Good luck!

## Datos de acceso al nivel
User: bandit32
Password: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
WELCOME TO THE UPPERCASE SHELL
>> ls
sh: 1: LS: Permission denied
>> ls -l
sh: 1: LS: Permission denied
>> man sh
sh: 1: MAN: Permission denied
>> sh -c ls
sh: 1: SH: Permission denied
>> sh -c ""^[[D$0
sh: 1: SH: Permission denied
>> sh -c "$0"
sh: 1: SH: Permission denied
>> $0
$ ls
uppershell
$ ls -lah
total 36K
drwxr-xr-x  2 root     root     4.0K Oct  5 06:19 .
drwxr-xr-x 70 root     root     4.0K Oct  5 06:20 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3.7K Jan  6  2022 .bashrc
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
-rwsr-x---  1 bandit33 bandit32  15K Oct  5 06:19 uppershell
$ whoami
bandit33
$ cat /etc/bandit_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
```
## Notas adicionales
*  sh es un intérprete de lenguaje de comando que ejecutar comandos leídos desde una cadena de línea de comando.
*  $0 es la variable que guarda el nombre del archivo/script donde se usa, pero si se escribe en la línea de comandos, se abre una nueva línea de comandos.
## Referencias
https://man7.org/linux/man-pages/man1/sh.1p.html
https://www.hostinger.mx/tutoriales/variables-en-bash