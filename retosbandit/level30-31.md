# Level 31

## Objetivo
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
User: bandit30
Password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit30@bandit:~$ mkdir /tmp/42101656/31
bandit30@bandit:~$ cd /tmp/42101656/31
bandit30@bandit:/tmp/42101656/31$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/42101656/31$ cd repo/
bandit30@bandit:/tmp/42101656/31/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/42101656/31/repo$ ls
README.md
bandit30@bandit:/tmp/42101656/31/repo$ git tag
secret
bandit30@bandit:/tmp/42101656/31/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/42101656/31/repo$
```
## Notas adicionales
*  Git tag permite dar etiquetas a commits o mostrar la etiqueta del commit actual.
*  Git show muestra los metadatos y los cambios de contenido de un commit.
## Referencias
https://dzone.com/articles/top-20-git-commands-with-examples