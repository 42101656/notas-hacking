# Level 12

## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

## Datos de acceso al nivel
User: bandit11
Password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit11@bandit:~$ ls -lah
total 24K
drwxr-xr-x  2 root     root     4.0K Oct  5 06:19 .
drwxr-xr-x 70 root     root     4.0K Oct  5 06:20 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3.7K Jan  6  2022 .bashrc
-rw-r-----  1 bandit12 bandit11   49 Oct  5 06:19 data.txt
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$
```
## Notas adicionales
* Rot13 es una especie de algoritmo de encriptación.
* El comando tr se usa para trasladar o eliminar caracteres.
* r 'A-Za-z' 'N-ZA-Mn-za-m' traslada todas las letras mayúsculas y minúsculas a sus caracteres ROT13 correspondientes.
## Referencias
https://en.wikipedia.org/wiki/ROT13
https://devicetests.com/decode-rot13-text-command-line