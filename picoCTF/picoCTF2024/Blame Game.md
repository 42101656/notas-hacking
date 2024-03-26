## Objetivo
Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/156/challenge.zip)

## Pistas

## Solución
1. Ir a terminal de Linux y hacer lo siguiente:
```
kali@kali:~/Documents/picoCTF/picoCTF2024$ mkdir blame_game

kali@kali:~/Documents/picoCTF/picoCTF2024$ cd blame_game/

kali@kali:~/Documents/picoCTF/picoCTF2024/blame_game$ wget https://artifacts.picoctf.net/c_titan/156/challenge.zip
--2024-03-19 19:58:33--  https://artifacts.picoctf.net/c_titan/156/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:26c9:1c00:16:5ec5:2840:93a1, 2600:9000:26c9:f200:16:5ec5:2840:93a1, 2600:9000:26c9:b200:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:26c9:1c00:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 293739 (287K) [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip                                              100%[=======================================================================================================================================>] 286.85K   483KB/s    in 0.6s    

2024-03-19 19:58:39 (483 KB/s) - ‘challenge.zip’ saved [293739/293739]


kali@kali:~/Documents/picoCTF/picoCTF2024/blame_game$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
 extracting: drop-in/message.py   
...


kali@kali:~/Documents/picoCTF/picoCTF2024/blame_game$ cd drop-in/

kali@kali:~/Documents/picoCTF/picoCTF2024/blame_game/drop-in$ ls
message.py

kali@kali:~/Documents/picoCTF/picoCTF2024/blame_game/drop-in$ cat message.py
print("Hello, World!"

kali@kali:~/Documents/picoCTF/picoCTF2024/blame_game/drop-in$ cat .git/logs/HEAD | grep picoCTF{
c9e851509190f5887e91339ee18087e3e77ebfda 0351e0474493168ca76441c24630c17554fd09ca picoCTF{@sk_th3_1nt3rn_d2d29f22} <ops@picoctf.com> 1710202021 +0000   commit: optimize file size of prod code

kali@kali:~/Documents/picoCTF/picoCTF2024/blame_game/drop-in$ 

```
2. La bandera es :
picoCTF{@sk_th3_1nt3rn_d2d29f22}
## Notas adicionales

## Referencias
