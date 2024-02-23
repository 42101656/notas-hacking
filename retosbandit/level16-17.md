# Level 17

## Objetivo
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Datos de acceso al nivel
User: bandit16
Password: JQttfApK4SeyHwDlI9SXGR50qclOAil1
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit16@bandit:~$ nmap -sV -p 31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2024-02-22 21:04 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00014s latency).
Not shown: 995 closed ports
PORT      STATE SERVICE     VERSION
31046/tcp open  echo
31518/tcp open  ssl/echo
31691/tcp open  echo
31790/tcp open  ssl/unknown
31960/tcp open  echo
32000/tcp open  tcpwrapped
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port31790-TCP:V=7.80%T=SSL%I=7%D=2/22%Time=65D7B709%P=x86_64-pc-linux-g
SF:nu%r(GenericLines,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20cu
SF:rrent\x20password\n")%r(GetRequest,31,"Wrong!\x20Please\x20enter\x20the
SF:\x20correct\x20current\x20password\n")%r(HTTPOptions,31,"Wrong!\x20Plea
SF:se\x20enter\x20the\x20correct\x20current\x20password\n")%r(RTSPRequest,
SF:31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20current\x20password\
SF:n")%r(Help,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20current\x
SF:20password\n")%r(SSLSessionReq,31,"Wrong!\x20Please\x20enter\x20the\x20
SF:correct\x20current\x20password\n")%r(TerminalServerCookie,31,"Wrong!\x2
SF:0Please\x20enter\x20the\x20correct\x20current\x20password\n")%r(TLSSess
SF:ionReq,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20current\x20pa
SF:ssword\n")%r(Kerberos,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x
SF:20current\x20password\n")%r(FourOhFourRequest,31,"Wrong!\x20Please\x20e
SF:nter\x20the\x20correct\x20current\x20password\n")%r(LPDString,31,"Wrong
SF:!\x20Please\x20enter\x20the\x20correct\x20current\x20password\n")%r(LDA
SF:PSearchReq,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20current\x
SF:20password\n")%r(SIPOptions,31,"Wrong!\x20Please\x20enter\x20the\x20cor
SF:rect\x20current\x20password\n");

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 98.48 seconds
bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 22 18:04:08 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 22 18:04:08 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 22 18:03:08 2024 GMT; NotAfter: Feb 22 18:04:08 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEWdQAXzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIyMTgwMzA4WhcNMjQwMjIyMTgwNDA4WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC0
EWB28TWVpVUtrYSaYvmbjtrgpiTuEqg01/SReTOErvDgCyz8mhJ06BhcWK0RDiNz
E1BeQ1s7bo4V8knTeqgTd3cA9XIKO8BgqmGwYiPJyBVDMO+9S4dojnuJGViyhoM7
e0kKwdp7+uEER22koJg+ZqyI/dSSmvaDqMAU+D6FKxcxKjF8vTQzn0CLsYSXPHxT
mhshEAC8jWhYggcUxG0L1qMJnh/NL18e0jwBeCrE2PwsRuh1Qc6vl4Fd/mUByDJb
KSjsR3zDoegCWzh5lTAbnt5eaT47PBNA4foRLypdCG1tG+Cbgk6d0BGtluAJz9D8
5vEfrVpm38OelPOo0vBJAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAl
z9TnfQ4cqpUeKMFRzhzuHEvuglEdfmmWmhpQ+NnpcI686OZDshzpHFRVUQjwMulr
XuhDoohLwnd+AOB4BqYWWYoF2z1mo3rsxZxxCoI7y8SP331O46Aqc4SyKMEfYBXq
mCaK5VQebSZotRPqI6jS2W7/+UmJXXKG4pEKI5pBA5tTnvNSbh6Yk87cFlAitTcN
36V1lq8S7tj2BZSfcC+nyoqwPPeLTb5beQTmKG0/JFDnYeHCbVQALq5AhXXH5G67
ytpppb4itSOMr9bfv+Awx6PPLbOJ/gxF1c1HkXX5/Pjbdy2W4sCykvXAJBir2BFe
ixo6bdA2sW0cz3uzk5x7
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 3617B2049442926C5C4A9BB6EBDA51ABB301DFD3C1282614B28F30548DC8BC5D
    Session-ID-ctx:
    Resumption PSK: F98A8A975362B623DA7A3FA0A3355F28A550E0B7F08EC9301C03290C8301E89E5BF2C43800EC330B6FF77EDC7F174277
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - d5 fe 56 7f 7c 44 0f 09-aa 20 5d ad 9d 9b 72 2f   ..V.|D... ]...r/
    0010 - c1 eb 52 0f 84 52 63 a4-c7 ee 30 54 38 6f 04 03   ..R..Rc...0T8o..
    0020 - 15 77 70 49 00 30 8a 29-0a 21 7d 96 49 fd 05 09   .wpI.0.).!}.I...
    0030 - fa 69 f4 4b 4c ae 50 7e-87 41 32 fd b6 bf af d7   .i.KL.P~.A2.....
    0040 - a2 de 84 63 5d f1 22 33-ea 85 7a ee e5 53 fa a3   ...c]."3..z..S..
    0050 - e3 31 77 7e bb 78 ba f7-e9 4c ed db 78 26 9f 89   .1w~.x...L..x&..
    0060 - 69 a9 60 04 61 9f 3d 0f-31 cd 33 f5 45 db c9 16   i.`.a.=.1.3.E...
    0070 - 51 57 ca 52 22 3e db 3b-98 c8 36 ba 4a 34 d3 bb   QW.R">.;..6.J4..
    0080 - ea 58 d0 5d bb 39 ca 6a-63 bf a6 9b 36 50 22 46   .X.].9.jc...6P"F
    0090 - 89 98 e1 d6 49 bf ee aa-2e 71 63 e0 40 d2 19 97   ....I....qc.@...
    00a0 - 97 64 d1 93 b3 66 6c 3b-da 47 55 0d 93 ae d5 d5   .d...fl;.GU.....
    00b0 - c3 f4 0b bb d9 4d 60 4b-e3 ea 96 6f 36 4d dd 4f   .....M`K...o6M.O
    00c0 - 1e 19 68 3a 99 2e fd 87-21 d1 41 73 97 06 62 f6   ..h:....!.As..b.

    Start Time: 1708636040
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 717963F8920A1628B76DD18CFDA0DD4FA7EE3E5FC77D46A31040E222C936ECB9
    Session-ID-ctx:
    Resumption PSK: DE397CF3C47A07B11349CA71471F5B01CF60E5411671E561ABFBFFC1D699DED9464C8280239ADB677EA764B686C0B9FB
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - d5 fe 56 7f 7c 44 0f 09-aa 20 5d ad 9d 9b 72 2f   ..V.|D... ]...r/
    0010 - 00 8a ea 48 c7 d0 2c 79-d6 8e f2 57 5c c4 2e 27   ...H..,y...W\..'
    0020 - 79 b0 da 2e 7e 95 ba 9c-ef 3c d5 44 88 ec e2 50   y...~....<.D...P
    0030 - ca 6d 06 92 7e 98 67 a2-4d 8b 97 10 38 4a 9d 30   .m..~.g.M...8J.0
    0040 - 10 c9 3b 3e 9a 6f a7 b7-20 b4 98 cb c5 45 a0 3d   ..;>.o.. ....E.=
    0050 - 77 f5 76 45 18 0e 76 2a-42 67 c2 8d a0 99 58 84   w.vE..v*Bg....X.
    0060 - c2 df 4f 61 b0 09 f0 58-a6 5e 9d a6 b5 f3 98 5b   ..Oa...X.^.....[
    0070 - 12 0a d7 9b d9 9b 34 15-7b 9c 78 0c 9f 61 66 24   ......4.{.x..af$
    0080 - 44 50 a0 ae 08 e7 a9 8c-d5 78 44 37 02 97 93 76   DP.......xD7...v
    0090 - f7 55 b5 60 fd 7d 55 ae-74 49 fd 3e 04 b0 50 2b   .U.`.}U.tI.>..P+
    00a0 - d8 27 ae eb c0 e3 5b 84-c5 32 10 a7 ce 6a f2 65   .'....[..2...j.e
    00b0 - 7a 11 a1 6a 88 e6 a0 82-ed 53 40 b5 57 ab 97 1e   z..j.....S@.W...
    00c0 - 4c a3 55 fe e0 cc 11 50-d0 ca 13 87 02 61 0a ac   L.U....P.....a..

    Start Time: 1708636040
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
bandit16@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:\Users\omar_>notepad private.key

C:\Users\omar_>ssh -i private.key bandit17@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames


      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * peda (https://github.com/longld/peda.git) in /opt/peda/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit17@bandit:~$ cat /etc/
Display all 214 possibilities? (y or n)
bandit17@bandit:~$ cat /etc/bandit_pass/bandit17
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
bandit17@bandit:~$
```
## Notas adicionales

* La opcion -vS detecta las versiones de los puertos.
* El comando notepad en windows sirve para abrir archivo en el Blog de Notas o crear uno nuevo.
## Referencias
https://nmap.org/man/es/man-version-detection.html
