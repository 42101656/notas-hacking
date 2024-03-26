## Objetivo
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/13/challenge.zip)

Additional details will be available after launching your challenge instance.

## Pistas

## Solución
1. Ir a terminal de Linux y hacer lo siguiente:
```
kali@kali:~/Documents/picoCTF/picoCTF2024$ mkdir scan_surprise

kali@kali:~/Documents/picoCTF/picoCTF2024$ cd scan_surprise/

kali@kali:~/Documents/picoCTF/picoCTF2024/scan_surprise$ wget https://artifacts.picoctf.net/c_atlas/13/challenge.zip
--2024-03-19 18:57:36--  https://artifacts.picoctf.net/c_atlas/13/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:26c9:fe00:16:5ec5:2840:93a1, 2600:9000:26c9:8200:16:5ec5:2840:93a1, 2600:9000:26c9:e00:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:26c9:fe00:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 740 [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip                                              100%[========================================================================================================================================>]     740  --.-KB/s    in 0s      

2024-03-19 18:57:42 (21.6 MB/s) - ‘challenge.zip’ saved [740/740]


kali@kali:~/Documents/picoCTF/picoCTF2024/scan_surprise$ unzip challenge.zip
Archive:  challenge.zip
   creating: home/ctf-player/drop-in/
 extracting: home/ctf-player/drop-in/flag.png  

kali@kali:~/Documents/picoCTF/picoCTF2024/scan_surprise$ cd home/ctf-player/drop-in/

kali@kali:~/Documents/picoCTF/picoCTF2024/scan_surprise/home/ctf-player/drop-in$ ls
flag.png

kali@kali:~/Documents/picoCTF/picoCTF2024/scan_surprise/home/ctf-player/drop-in$ sudo apt install zbar-tools
[sudo] password for kali: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
...

kali@kali:~/Documents/picoCTF/picoCTF2024/scan_surprise/home/ctf-player/drop-in$ zbarimg flag.png
QR-Code:picoCTF{p33k_@_b00_d4ca652e}
scanned 1 barcode symbols from 1 images in 0.02 seconds



```
2. La bandera es :
picoCTF{p33k_@_b00_d4ca652e}
## Notas adicionales

## Referencias
https://www.baeldung.com/linux/read-qr-codes