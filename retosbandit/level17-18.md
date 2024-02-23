# Level 18

## Objetivo
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**.

## Datos de acceso al nivel
User: bandit17
Password: VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit17@bandit:~$ ls -lah
total 36K
drwxr-xr-x  3 root     root     4.0K Oct  5 06:19 .
drwxr-xr-x 70 root     root     4.0K Oct  5 06:20 ..
-rw-r-----  1 bandit17 bandit17   33 Oct  5 06:19 .bandit16.password
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3.7K Jan  6  2022 .bashrc
-rw-r-----  1 bandit18 bandit17 3.3K Oct  5 06:19 passwords.new
-rw-r-----  1 bandit18 bandit17 3.3K Oct  5 06:19 passwords.old
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
drwxr-xr-x  2 root     root     4.0K Oct  5 06:19 .ssh
bandit17@bandit:~$ diff passwords.old passwords.new --color
42c42
< p6ggwdNHncnmCNxuAt0KtKVq185ZU7AW
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$ diff passwords.old passwords.new --color | paste -s -d ' '
42c42 < p6ggwdNHncnmCNxuAt0KtKVq185ZU7AW --- > hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$ diff passwords.old passwords.new --color | paste -s -d ' ' | sed 's/.*> //'
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$
```
## Notas adicionales

* El comando diff compara el contenido de dos archivos y muestra las diferencias entre ellos
* paste -s -d ' ' elimina los saltos de línea sin contar el último.
## Referencias
https://www.geeksforgeeks.org/diff-command-linux-examples/
https://unix.stackexchange.com/questions/114244/replace-all-newlines-to-space-except-the-last
