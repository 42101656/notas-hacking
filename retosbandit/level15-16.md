# Level 16

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**.

## Datos de acceso al nivel
User: bandit15
Password: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 20 17:50:06 2024 GMT; NotAfter: Feb 20 17:51:06 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEIivS1jANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIwMTc1MDA2WhcNMjQwMjIwMTc1MTA2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC4
XC9dgne8ha9I/vXn4uTtObLhI/PPyLyl4jyDQPp61VtsEMcOb95KhXxdtQiDtzSD
3KXQVFLaPlVGKDWSR9nV+GoazSNPmNLH/IMVrUYxXjYikPxo1jjYKyuqfjV5bNm3
Hz6z4eDl7wNbPRaPAMPo0WU23m9M04bKQHLINfN7Abz3a+7ChLeICrWXiXp9mWfj
PY8cK7Vayz0eHU4Lg64q4jUaXQqZ/ta1RqZEwv7ZuTKctcazpK/u2+h4zvQCPyLh
uDjUXZTLlIuhfjyKUJLQsmYHAQprV6sY3ybFN32dW6MSE0/ApT6Th0LzKeaYxk5b
3NIeaYyPeKsjqFSwy+2zAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBQ
RXG1k+cB357X43fsiyaCQQh4RbWHOcg1jBes5eiC/H8MyC3ec1znXvOUfqJcWNQJ
9UJDMwbkpo+IcwJiOe9n/D3Zeypv1g+ta8KKLsQ+zcbp5RdltKy7GuO/s5WjVofE
/IHz/5g+IMoqqYLlquQ539CZykPMC9TB9uWfJj/i8faCox4gjtkSCri+27tUZuHi
eYR3zxY1ptsJti/pMaItC6Oc2/pSlotQ4fXdciLZYGXqlmSFBt8Y8/v1YkhME5gN
3HmBV/Zg1SghA57zYsbf3npvQwudr04f2iF493pe0VRN6DfiXTxWkJe1VKuyGHEr
Q4L4OdVlgMSeyYyKgFc7
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
    Session-ID: 063427A05A3D3C7D2A2528412E2E3BA0BDB54E62449ADE9FDB745862C03E2C01
    Session-ID-ctx:
    Resumption PSK: 7F8C1E1CE59EE36808BD315D5429CB14D91B43E9FC6733C77FA0EF51272F4B1E1565B4FD042ACC58D3D5CBBA48C109A8
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 81 c9 7a 81 90 61 a2 44-6e 83 ab 39 4b a2 9f d6   ..z..a.Dn..9K...
    0010 - dc eb 89 26 d4 5d 7c 1c-cc 88 a2 12 1f b7 7d e8   ...&.]|.......}.
    0020 - 9a d8 1a ba 04 8d 36 1e-5f f6 90 cf db f3 5c d9   ......6._.....\.
    0030 - 04 e9 27 91 50 cb 8e dc-8a 96 ea 4b 3e 7c e9 55   ..'.P......K>|.U
    0040 - e1 1e 27 b8 63 51 0b 6b-d9 53 02 2d f6 72 05 ad   ..'.cQ.k.S.-.r..
    0050 - ff 35 15 d3 d2 77 07 7b-f2 3b fb 1a 36 d4 75 df   .5...w.{.;..6.u.
    0060 - 61 ac 5a 6a db df bd fe-a7 75 4d 79 b4 56 c6 39   a.Zj.....uMy.V.9
    0070 - 2f 5c 2e f7 87 6b 6d 77-be f7 6a be 77 6f 01 5d   /\...kmw..j.wo.]
    0080 - 49 45 86 32 89 2d 1f 27-87 6e 73 2f 66 07 48 06   IE.2.-.'.ns/f.H.
    0090 - c5 63 30 41 bf 75 f8 ce-9d bf a0 06 f5 db c4 2a   .c0A.u.........*
    00a0 - a7 e8 af 1d 5f 60 0b 00-9d 95 cf ab 9e 4f 2f e5   ...._`.......O/.
    00b0 - e6 50 1b 45 ca b9 95 6c-5d 3a e8 40 21 ed 20 89   .P.E...l]:.@!. .
    00c0 - dc b2 3b 63 0c 16 cb 2d-8a 66 fe 84 7e a9 68 15   ..;c...-.f..~.h.

    Start Time: 1708456946
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
    Session-ID: D477C46A9B226EFE19D0AD009519EB2A564C12163110D4892FC0B2AC7AECD661
    Session-ID-ctx:
    Resumption PSK: FB945AD9C6031BF5669032FF256A3428B96597895DB9DAB6B4C4E5BFCA4CD98E541A464E440D67F6BC96668D8A7F2A19
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 81 c9 7a 81 90 61 a2 44-6e 83 ab 39 4b a2 9f d6   ..z..a.Dn..9K...
    0010 - c2 8b 13 5b 7b f9 e9 12-6c fe 1e 32 e5 21 dd 66   ...[{...l..2.!.f
    0020 - ae b3 e6 74 f6 e2 2f 3c-06 5c c8 d4 0c 36 95 7d   ...t../<.\...6.}
    0030 - 92 c5 5a 8a 30 d1 bd 56-82 66 7b 23 20 43 03 1e   ..Z.0..V.f{# C..
    0040 - 62 1c f4 6f 76 7c bc 43-e2 a0 c7 66 80 cd 0b d3   b..ov|.C...f....
    0050 - ea f9 b6 df 01 1a c6 06-29 f6 15 4b 90 fa 7b 94   ........)..K..{.
    0060 - f4 1a 00 e3 f0 fe 53 72-02 19 d1 b7 9e 09 ca 1f   ......Sr........
    0070 - 70 46 19 50 87 dd 95 ce-87 9b 9a e1 62 5b 4c 6b   pF.P........b[Lk
    0080 - 1a cb b9 bc 84 68 66 45-c3 1f 21 5e 58 e5 cf 4c   .....hfE..!^X..L
    0090 - 28 3a 8a 32 35 bf e2 f3-26 cf 0a 0a 2f 65 43 15   (:.25...&.../eC.
    00a0 - 8f fb fc f9 67 9d 50 a8-fc 17 58 8e 15 56 3c 9b   ....g.P...X..V<.
    00b0 - 81 8f 43 3f 6a 44 76 a0-8c e4 04 a3 79 86 53 8a   ..C?jDv.....y.S.
    00c0 - a9 ec 67 52 a9 4e 00 fd-54 82 f9 4e 98 d3 80 d2   ..gR.N..T..N....

    Start Time: 1708456946
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$
```
## Notas adicionales

* Pruebe la conectividad SSL con los comandos s_client para comprobar si el certificado es válido, confiable y completo.
* La opcion -connect prueba la conectividad a un servicio HTTPS.
## Referencias
https://docs.pingidentity.com/r/en-us/solution-guides/htg_use_openssl_to_test_ssl_connectivity
