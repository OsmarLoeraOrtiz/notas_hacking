# Bandit Level15

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de acceso
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solucion
```bash
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  1 06:31:12 2022 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  1 06:31:12 2022 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  1 06:30:12 2022 GMT; NotAfter: Sep  1 06:31:12 2022 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEHn8h8jANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjIwOTAxMDYzMDEyWhcNMjIwOTAxMDYzMTEyWjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDK
u/UD6yArwj259J4o2IVQQGvM/oGVIiYYppFd1jxltmQ03SOUVg+4px+7qOJuCbxA
AH9NCAl55r7v/VDlwGkpu4c2GaqR3zSAlidrtJjrVFZP/QilXdv0uV35N4i30BuT
DdI+FzlYcQx7ztZdtDxp61FTjET4BIcFmSzMQLitpYeeiVcKLXTPnsF8216drWjQ
0Ucb+3RvGgPo/rKPra8/7WYFa8ALdnu2rwP07ndtMDL3iJF9VMuBsr8UuTdsktwa
174QGx0f3RFkcKJ1foxYnSoHvy0BhxVGguMKuinY6cyLELwnjcAp4A2oGI438GnV
whe39ZlCkGved612QLhDAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQDE
2X2mgxYDvujnIAL2Qbs8JnUBFe3lZsRZJbPgko3MZ4lScB5Rbz+vb6q6s0KGGMjh
sKweg4BtG4sQWDIwX2yd4XwJa8rrGWuoA4kgCQ/jJhFZrbCPbDN3sbzX8Tql+epd
oJyQcvLOkWDazRPgx0i4dMXIgUv0kbE+NCvj2waXHldMyjT6GFL2bdv/Xd8ffnXg
wlggJKKIzl0RMp/5z5n1bPMoLVl5HcUG3UzOsTcqcSThTr3JXeWLjaL0qJfAfcw5
V+GM2tGTQB3c4jvISAl5RAARpvFUMc4d4hKd6aesRcFHZfbtSjxglPFmeL1VGxJ9
EIg5c/xwHOE6dgDA2WdS
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
    Session-ID: FD6F6B9894E3579DC9A87CE67524C3696189B5EB55881980D4D1752B657DB57F
    Session-ID-ctx:
    Resumption PSK: E540D605CD7250C90A49A5E387BA4A2BA9CB6FED036D5731091200660FE73BDA46556838D05B939FC76633B4523038E6
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 09 86 a0 aa 25 48 38 1d-0e b1 8d f8 fa 82 ac 33   ....%H8........3
    0010 - 57 d0 03 34 fa c3 17 ee-e4 21 27 5d c8 a0 5b b3   W..4.....!']..[.
    0020 - 0e 07 e2 aa fd a7 23 02-c1 06 a4 68 c7 91 04 3e   ......#....h...>
    0030 - 14 b5 71 af 10 a2 51 2f-0c c1 9d 0a ca 71 79 c4   ..q...Q/.....qy.
    0040 - bb db 32 5c f5 a5 0a d0-78 a2 02 6a 9d 53 b2 89   ..2\....x..j.S..
    0050 - 00 3b ee dc 4b 58 63 95-e6 02 ee 21 94 af ce 83   .;..KXc....!....
    0060 - be 5a 29 a3 ec 0b e4 d8-d2 b1 2c d4 e0 d9 db 97   .Z).......,.....
    0070 - 7b cf 69 0b e4 af b9 1c-94 ec 87 cf 67 1e 69 b1   {.i.........g.i.
    0080 - 25 68 52 19 80 ad 25 89-b4 1e 72 9c e2 7b 07 05   %hR...%...r..{..
    0090 - ec 42 57 e9 ab b2 d4 1c-68 03 76 ba 7f 44 7a 7d   .BW.....h.v..Dz}
    00a0 - 5a 40 77 88 01 8e af e9-d5 93 0a 82 f1 31 d4 35   Z@w..........1.5
    00b0 - 98 cc 5f c2 59 37 a7 77-87 7c 55 b2 c5 98 79 47   .._.Y7.w.|U...yG
    00c0 - 6b 6b 6e 8e c8 ad d7 46-60 58 b1 b8 b8 96 c3 54   kkn....F`X.....T

    Start Time: 1662267125
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
    Session-ID: 2E12360F25A13FB334C061BCC447A7B49C1EEDFD9B8F096FE859E8D04A40EC8F
    Session-ID-ctx:
    Resumption PSK: C20016B0DFB32CFB32A7EEC9EE982F3783D0AE0B0D63F67F8F1552A2C73EEC6CFCA7705FBC6170BFF5580D3AD1B28E45
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 09 86 a0 aa 25 48 38 1d-0e b1 8d f8 fa 82 ac 33   ....%H8........3
    0010 - 01 06 5d 51 55 6f 83 9d-30 dd cd 4b 2a 36 b7 75   ..]QUo..0..K*6.u
    0020 - dd fd 66 5c 93 c7 34 c3-8d 43 da 8f 2f a8 4c 0d   ..f\..4..C../.L.
    0030 - e8 14 d5 4e 94 e3 ea 54-96 4c 0e f6 0d 2a a9 0f   ...N...T.L...*..
    0040 - 1e 0b 58 7e 1d 84 a0 0d-b0 3b 86 2d 41 62 9d c0   ..X~.....;.-Ab..
    0050 - 52 b2 cf 97 3c 65 d3 e6-63 08 f7 f4 3b ac ce 88   R...<e..c...;...
    0060 - 28 5e ba d4 60 7d 56 0d-68 0b 17 e2 c0 ee 71 41   (^..`}V.h.....qA
    0070 - ec d4 95 93 a1 69 7b 9d-a2 b3 63 ed 15 f0 78 28   .....i{...c...x(
    0080 - 20 b3 d9 2a 46 79 e3 f0-05 bb 09 c1 53 03 5b 94    ..*Fy......S.[.
    0090 - 05 62 ca a5 bc 6e 35 cf-1c 6f 3d cb a0 29 ba ad   .b...n5..o=..)..
    00a0 - cb c8 33 a5 f9 32 83 e8-44 dd d9 a3 b2 de af be   ..3..2..D.......
    00b0 - 87 77 a1 fc 2d 9c 6b 60-7c 64 c2 41 ff ca 69 a0   .w..-.k`|d.A..i.
    00c0 - c2 19 a6 6c ad 9d b4 a1-76 e3 52 3f 06 c2 23 fc   ...l....v.R?..#.

    Start Time: 1662267125
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

## Referencias