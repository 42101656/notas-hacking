# Level 15

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

## Datos de acceso al nivel
User: bandit14
Password: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit14@bandit:~$ ls -lah
total 24K
drwxr-xr-x  3 root root 4.0K Oct  5 06:19 .
drwxr-xr-x 70 root root 4.0K Oct  5 06:20 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3.7K Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
drwxr-xr-x  2 root root 4.0K Oct  5 06:19 .ssh
bandit14@bandit:~$ echo "fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq" | nc localhost 30000
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

bandit14@bandit:~$
```
## Notas adicionales
* Mediante el comando `nc` puedes conectarte a los puertos **TCP/UDP** de un host. De este modo podrás conectarte otros servidores usando diferentes protocolos de red. Además, también es posible crear servidores que se mantengan a la escucha de peticiones entrantes. Los puertos se abrirán por defecto mediante el protocolo **TCP**, aunque también se acepta el protocolo **UDP** 
## Referencias
https://www.neoguias.com/comando-nc/
