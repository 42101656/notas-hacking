# Level 5

## Objetivo
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

## Datos de acceso al nivel
User: bandit4
Password: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit4@bandit:~$ ls -l
total 4
drwxr-xr-x 2 root root 4096 Oct  5 06:19 inhere
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls -lh
total 40K
-rw-r----- 1 bandit5 bandit4 33 Oct  5 06:19 -file00
-rw-r----- 1 bandit5 bandit4 33 Oct  5 06:19 -file01
-rw-r----- 1 bandit5 bandit4 33 Oct  5 06:19 -file02
-rw-r----- 1 bandit5 bandit4 33 Oct  5 06:19 -file03
-rw-r----- 1 bandit5 bandit4 33 Oct  5 06:19 -file04
-rw-r----- 1 bandit5 bandit4 33 Oct  5 06:19 -file05
-rw-r----- 1 bandit5 bandit4 33 Oct  5 06:19 -file06
-rw-r----- 1 bandit5 bandit4 33 Oct  5 06:19 -file07
-rw-r----- 1 bandit5 bandit4 33 Oct  5 06:19 -file08
-rw-r----- 1 bandit5 bandit4 33 Oct  5 06:19 -file09
bandit4@bandit:~/inhere$ file ./-file0*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat "-file07"
cat: invalid option -- 'f'
Try 'cat --help' for more information.
bandit4@bandit:~/inhere$ cat "./-file07"
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
bandit4@bandit:~/inhere$


```
## Notas adicionales
* El comando file sirve para determinar el tipo de archivo.
* El . antes de / sirve para indicar que el archivo se encuentra en el directorio actual.
## Referencias
