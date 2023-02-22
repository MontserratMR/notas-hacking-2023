## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command**

## Datos Acceso
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

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
notAfter=Feb 21 22:03:56 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 21 22:03:56 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 21 22:02:56 2023 GMT; NotAfter: Feb 21 22:03:56 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEF3vcjDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMjIxMjIwMjU2WhcNMjMwMjIxMjIwMzU2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCg
1elREdWTbtCZNl7KNMjleNrcG71f9lZhjAfM4x+TDwlPpT+Q9O3V6J687fJdMH85
xfUwcZG0XFCeN1nxnmQadGF/ZHEt0laWmCQfo5LogzgGFcaZWC1a6XZ5ZKv7SRDt
tvPK/CTKwOJD5ZJVEXEk9R8YQ/VbKwZMDc43WD/HKypvBv7fZVbJkKYY75LOby86
7gux29Emhntj5pZyYagYbmonnAiw6447bGTC1d6jilGPhXMzckTI57WGeNdp4ppL
3pXSVDLOU2XJ8Um/L2VIgGTsUk5CwrtzVxyt6I5sKavUhsNGlzqvHI/McgbsnHi8
3LDg9k/Co8F21eZFooVlAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBz
lgp6XhMshglRxhxHRg1xHkVYSFSBaS5Adq5OIoE/oetyedTiO2B9MLmNZ9Juu/WK
/+WZFmNdzQ6Iw5ueBz/rmY+DvzTjjd4CPPqeilG5mngceR5nliM9mXkpQlmm3T1a
8JuBrDugrN9BP4IeBTER0pgQcQvsRATrv/SAVFVBhTSvOKFhoYNEdBzaqxclEjD6
bl3UkzNag/S3iLuv24xoQkMmlFC2afaswkG/cQ4p3BuapuZORjbohUOXS24QDl0z
A2RDFNizi42ZVJ8ZW1qbURZ4n/VbIAi7vRHldPKjC8hYAcdvUekB0schBlc1J06Z
phGCgzTVUzJu9yz8uKzO
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
    Session-ID: B2517AF305E7379B0AC6D0F5655BB52B2BFEB19B39060EC6C0D95739B1A7268C
    Session-ID-ctx:
    Resumption PSK: 7D8086FD587EC4AC60A947C8B2B6102857F17201D12BCE5A9A7507D5BE91FF99FFDB27627A564C950D57D6897EFA1B32
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - a5 3d 92 1f d1 78 36 48-bb a6 da 4d 19 13 ee a7   .=...x6H...M....
    0010 - 86 1e 68 38 63 33 9c 80-b9 70 77 5b ff d0 fd 23   ..h8c3...pw[...#
    0020 - 5d c0 26 19 2b 17 4d c7-f7 6a fa 4f c2 41 24 99   ].&.+.M..j.O.A$.
    0030 - 2d 07 05 ae c5 ad 30 f8-7b b6 64 7f 94 df 72 27   -.....0.{.d...r'
    0040 - 8d f4 01 fe fb 1a 51 d7-a2 31 67 a9 c2 59 4d ff   ......Q..1g..YM.
    0050 - 05 5a 03 49 14 11 80 58-a9 e9 21 d5 6e 08 eb 56   .Z.I...X..!.n..V
    0060 - 1f 6c c5 67 d4 f6 27 0e-21 9a 9d 54 c3 d5 35 28   .l.g..'.!..T..5(
    0070 - 86 7c 6e 5c 7e 11 79 1d-47 8c 61 d6 a0 13 82 bf   .|n\~.y.G.a.....
    0080 - 9a f2 46 c7 69 34 bc ee-8e 7e 43 c5 29 b7 10 f7   ..F.i4...~C.)...
    0090 - 7f fb a7 17 1b a2 8f 72-0e ac 78 8e 86 6a 03 c2   .......r..x..j..
    00a0 - 91 b3 6d 36 5d ae 1c 00-27 af 82 16 f6 f9 59 be   ..m6]...'.....Y.
    00b0 - 7c a8 58 d4 d5 e6 b6 5f-44 75 6c 68 ae d9 73 78   |.X...._Dulh..sx
    00c0 - 91 ed ff a9 9e 65 9f 08-35 33 3c ee a3 32 f2 d8   .....e..53<..2..

    Start Time: 1677035804
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
    Session-ID: 1496C35D9BD3746D80CE293747E80E92EFCB4DB6C8CC958E785EBC52D740EFC4
    Session-ID-ctx:
    Resumption PSK: 213E55DFFF6FA63D405941776606E398D857F55E8E554A4D68EFCB20C585321E3BACA989B7F84671E541EB5F84FA6AE1
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - a5 3d 92 1f d1 78 36 48-bb a6 da 4d 19 13 ee a7   .=...x6H...M....
    0010 - c5 13 f0 99 6b 9d cf 7d-31 70 d7 f9 59 b6 69 b1   ....k..}1p..Y.i.
    0020 - 02 33 70 fa 1e d2 68 bb-24 78 88 0f 5f eb ee ad   .3p...h.$x.._...
    0030 - b5 7e 0f bb 1c ec 20 5f-b6 6f a0 d2 9e c3 9c 95   .~.... _.o......
    0040 - bb 43 3d 33 3d b5 53 15-bc b8 50 8b a1 a2 c3 80   .C=3=.S...P.....
    0050 - dd 4b 83 59 d7 9e 6f a9-06 e6 b8 d1 3a 77 ab 4b   .K.Y..o.....:w.K
    0060 - 1e f8 50 cb 2d 91 4f a2-f5 27 8e 08 9e 99 61 41   ..P.-.O..'....aA
    0070 - 7d b5 c0 4a e3 e9 6d 7a-9d 75 2b 76 53 6c 57 0e   }..J..mz.u+vSlW.
    0080 - 17 d6 a1 96 75 20 b9 67-7d f0 5d 45 dd 41 75 3f   ....u .g}.]E.Au?
    0090 - 39 b7 45 76 67 d0 87 3c-ec 43 40 a3 46 ba e8 f4   9.Evg..<.C@.F...
    00a0 - 7c 9e 4d ba 30 16 ed a1-6d 59 30 5d 11 ad 98 49   |.M.0...mY0]...I
    00b0 - e7 5d 55 e0 d4 c9 5f 52-27 af a6 38 d6 7c a7 38   .]U..._R'..8.|.8
    00c0 - 17 dd dd 66 2e 78 2d 4a-79 4c 42 c7 b0 c8 b6 fc   ...f.x-JyLB.....

    Start Time: 1677035804
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1
```

## Notas Adicionales
* El comando s_client implementa un cliente SSL/TLS genérico que se conecta a un host remoto mediante SSL/TLS. Es una herramienta de diagnóstico muy útil para servidores SSL.
* OpenSSL es una herramienta de línea de comandos de código abierto que se usa comúnmente para generar claves privadas, crear CSR, instalar su certificado SSL/TLS e identificar la información del certificado.

## Referencias
-   [Secure Socket Layer/Transport Layer Security on Wikipedia](https://en.wikipedia.org/wiki/Secure_Socket_Layer)
-   [OpenSSL Cookbook - Testing with OpenSSL](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)