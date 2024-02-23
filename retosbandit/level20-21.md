# Level 21

## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think

## Datos de acceso al nivel
User: bandit20
Password: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit20@bandit:~$ ls -lah
total 36K
drwxr-xr-x  2 root     root     4.0K Oct  5 06:19 .
drwxr-xr-x 70 root     root     4.0K Oct  5 06:20 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3.7K Jan  6  2022 .bashrc
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
-rwsr-x---  1 bandit21 bandit20  16K Oct  5 06:19 suconnect
bandit20@bandit:~$ ./suconnect
Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.
bandit20@bandit:~$ cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ nc -lnvp 1010 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 1042812
bandit20@bandit:~$ nc: Permission denied
nc -lnvp 2010 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[2] 1043021
[1]   Exit 1                  nc -lnvp 1010 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ Listening on 0.0.0.0 2010
./suconnect 2010
Connection received on 127.0.0.1 46420
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[2]+  Done                    nc -lnvp 2010 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$
```
## Notas adicionales

*  -l: Sirve para que Netcat abra un puerto y se mantenga ala escucha. Se aceptará una única conexión de un único cliente antes de cerrarse.
- -p: Esta opción permite especificar el puerto al que conectarse.
- -v: Se usa para mostrar información acerca de la conexión.
## Referencias
https://www.neoguias.com/comando-nc