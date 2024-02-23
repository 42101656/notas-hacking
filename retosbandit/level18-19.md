# Level 19

## Objetivo
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

## Datos de acceso al nivel
User: bandit18
Password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
C:\Users\omar_>ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:

awhqfNnAbc1naukrpqDYcF95h7HoMTrC

C:\Users\omar_>
```
## Notas adicionales

* Se puede ejecutar comandos sin necesidad de estar en la terminal del host simplemente escribiendo el comando después de todo el comando ssh.
## Referencias
https://www.geeksforgeeks.org/how-to-execute-commands-remotely-using-ssh-in-linux/