# Level 6

## Objetivo
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

## Datos de acceso al nivel
User: bandit5
Password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit5@bandit:~$ ls -l
total 4
drwxr-x--- 22 root bandit5 4096 Oct  5 06:19 inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls -l
total 80
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere00
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere01
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere02
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere03
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere04
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere05
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere06
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere07
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere08
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere09
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere10
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere11
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere12
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere13
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere14
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere15
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere16
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere17
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere18
drwxr-x--- 2 root bandit5 4096 Oct  5 06:19 maybehere19
bandit5@bandit:~/inhere$ find . -type f -size 1033c -not -executable
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
bandit5@bandit:~/inhere$
```
## Notas adicionales
* La opción -type  f sirve para mostrar solo los archivos.
* La opción -size 1033c sirve para buscar archivos que tengan un tamaño de 1033 bytes, la letra c es por byte.
* La opción -not -executable indica que el archivo no debe ser ejecutable.
## Referencias
https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/