## Objetivo
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.You can download the challenge files here:

- `[challenge.zip](https://artifacts.picoctf.net/c_rhea/20/challenge.zip)`

Additional details will be available after launching your challenge instance.
## Pistas
You can create a SHA checksum of a file with `sha256sum <file>` or all files in a directory with `sha256sum <directory>/*`.
## Solución
1. Ir a terminal de Linux y hacer lo siguiente:
```
kali@kali:~/Documents/picoCTF/picoCTF2024/verify$ ssh -p 59561 ctf-player@rhea.picoctf.net
The authenticity of host '[rhea.picoctf.net]:59561 ([3.136.191.228]:59561)' can't be established.
ED25519 key fingerprint is SHA256:QKdv+RGJL0UYRDM66IiGQ5dsXOX7DQFqB7umTylh+IU.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[rhea.picoctf.net]:59561' (ED25519) to the list of known hosts.
ctf-player@rhea.picoctf.net's password:  f3b61b38
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1014-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@pico-chall$ ls
checksum.txt  decrypt.sh  files
ctf-player@pico-chall$ cat checksum.txt
fba9f49bf22aa7188a155768ab0dfdc1f9b86c47976cd0f7c9003af2e20598f7
ctf-player@pico-chall$ sha256sum files/* | grep fba9f49bf22aa7188a155768ab0dfdc1f9b86c47976cd0f7c9003af2e20598f7
fba9f49bf22aa7188a155768ab0dfdc1f9b86c47976cd0f7c9003af2e20598f7  files/87590c24
ctf-player@pico-chall$ ./decrypt.sh files/87590c24
picoCTF{trust_but_verify_87590c24}
ctf-player@pico-chall$ 
```
2. La bandera es :
picoCTF{trust_but_verify_87590c24}
## Notas adicionales

## Referencias
https://man.archlinux.org/man/sha256sum.1.es