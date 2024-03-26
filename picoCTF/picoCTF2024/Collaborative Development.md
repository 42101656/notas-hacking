## Objetivo
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/176/challenge.zip)

## Pistas
`git branch -a` will let you see available branches

## Solución
1. Ir a terminal de Linux y hacer lo siguiente:
```
kali@kali:~/Documents/picoCTF/picoCTF2024$ mkdir Collaborative_Development
        
kali@kali:~/Documents/picoCTF/picoCTF2024$ cd Collaborative_Development/

kali@kali:~/Documents/picoCTF/picoCTF2024/Collaborative_Development$ wget https://artifacts.picoctf.net/c_titan/176/challenge.zip
--2024-03-19 20:06:03--  https://artifacts.picoctf.net/c_titan/176/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:24db:9400:16:5ec5:2840:93a1, 2600:9000:24db:d000:16:5ec5:2840:93a1, 2600:9000:24db:e600:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:24db:9400:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24474 (24K) [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip                                              100%[=======================================================================================================================================>]  23.90K  --.-KB/s    in 0.08s   

2024-03-19 20:06:09 (291 KB/s) - ‘challenge.zip’ saved [24474/24474]


kali@kali:~/Documents/picoCTF/picoCTF2024/Collaborative_Development$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
   creating: drop-in/.git/
...
kali@kali:~/Documents/picoCTF/picoCTF2024/Collaborative_Development$ cd drop-in/

kali@kali:~/Documents/picoCTF/picoCTF2024/Collaborative_Development/drop-in$ python flag.py
Printing the flag...

kali@kali:~/Documents/picoCTF/picoCTF2024/Collaborative_Development/drop-in$ git branch -a
  feature/part-1
  feature/part-2
  feature/part-3
* main

kali@kali:~/Documents/picoCTF/picoCTF2024/Collaborative_Development/drop-in$ git checkout feature/part-1
Switched to branch 'feature/part-1'

kali@kali:~/Documents/picoCTF/picoCTF2024/Collaborative_Development/drop-in$ python flag.py
Printing the flag...
picoCTF{t3@mw0rk_
kali@kali:~/Documents/picoCTF/picoCTF2024/Collaborative_Development/drop-in$ git checkout feature/part-2
Switched to branch 'feature/part-2'

kali@kali:~/Documents/picoCTF/picoCTF2024/Collaborative_Development/drop-in$ python flag.py
Printing the flag...
m@k3s_th3_dr3@m_
kali@kali:~/Documents/picoCTF/picoCTF2024/Collaborative_Development/drop-in$ git checkout feature/part-3
Switched to branch 'feature/part-3'

kali@kali:~/Documents/picoCTF/picoCTF2024/Collaborative_Development/drop-in$ python flag.py
Printing the flag...
w0rk_2c91ca76}

```
2. La bandera es :
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_2c91ca76}
## Notas adicionales

## Referencias
