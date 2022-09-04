# Bandit Level16

## Objetivo
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it

## Datos de acceso
bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Solucion
```bash
bandit16@bandit:~$ nmap -p31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2022-09-04 05:06 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.000096s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.06 seconds
bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  3 23:40:42 2022 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  3 23:40:42 2022 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  3 23:39:42 2022 GMT; NotAfter: Sep  3 23:40:42 2022 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEPBAeDzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjIwOTAzMjMzOTQyWhcNMjIwOTAzMjM0MDQyWjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDJ
oaGloiCj5rvCVLShjf7nTU9pTzioKE5KGG7ac3eq6yO+3wHqMTwCFvqrNB4ZjcLD
Kbttx2enLnHU3ncVxb42sf+vez3L6nfnXYcEyRRB2Cmq5ndVxhDCfMXd0jQVkzF+
388rJNbfEr5xSR7YznfHllQLGLV08G92mmjsPv7+adPyEZ5M6/2gC8OdOmr3J1lE
CD9M7DcYz9zeAZ5ri0l7IF/hghbiuRNVywVFe9jRLCoaGs1a4eWvUe4qwAvuZ9Dt
38Fix1XaaHZK6BOUkelh7lP/ZDQdEck2W7/8V+hHR0cd7ZJb7Emn8WdaXf04786b
n721Grcm2HXIbpZaAHrNAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQCK
REInXE2/tbk1lkCo8B/79Ckpq3sX/gHB+Q8aXuQNqlTTTUMwiHRdnnuC2imoqoq9
dHYOuhWpAoqKhAyezQkj7WtTjTXfT8ViNWzxPQcPUki1ERlQIRgZc/IGgW6jbzzg
PEfJiuIKr56lC/zFQkL7L9iusSopSGQGvz8rJz9YsOIHDycWhFQaJFFnpySQJOp1
RjSfZvKWuWloSCxyLrp0RdAWHpfshUh3UZQxqP5NzbNR6hCXh5o/1WqCS9RHkviS
LY3tn2wUJPX2DexmpAh+NzfimKN4UMKijnvmIRNF1Kd6TEidT8cZRvXnUnNkm/qg
LzdmlimtXnifHPGCsmXp
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
    Session-ID: F48FC8CAD669898BEB284ADDE9A3458E70FA5CC1864FC9E98FFB3D24B4657C2A
    Session-ID-ctx:
    Resumption PSK: 20A85C5352BC23C131F8BB250A314D2BCCE0855348FFC30E90EB91AE46FD44B982C05352013F486685B182A615D79D55
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - fb 34 dc b1 cc 2b c6 d3-52 56 11 ae 76 76 80 c3   .4...+..RV..vv..
    0010 - da b5 d4 6b 9a ac ca ff-d8 f0 86 c7 02 02 ea 45   ...k...........E
    0020 - 47 27 34 23 a7 ed 0f 99-e4 05 72 eb 4b e3 ec f3   G'4#......r.K...
    0030 - 84 4d 4d 86 f3 3c bd 7e-9e 1d 59 e6 2b 2d 0c e9   .MM..<.~..Y.+-..
    0040 - f6 46 06 d1 48 1b 32 c8-30 10 a5 af 5c 3f 43 70   .F..H.2.0...\?Cp
    0050 - 70 1b 42 74 a0 f7 2e 14-ec a8 ad c4 c3 1a f9 74   p.Bt...........t
    0060 - 22 73 e8 45 33 09 e8 95-d0 a1 d4 5f d1 c8 2a ea   "s.E3......_..*.
    0070 - 87 74 72 2f 89 5f 63 8b-a4 18 81 7a a3 28 2f bd   .tr/._c....z.(/.
    0080 - 32 4f d6 4e ea 89 f2 83-29 fc 4a 20 9d 85 97 e7   2O.N....).J ....
    0090 - 2d c1 d1 59 40 18 db 63-3c 6d b9 40 19 cb 0f dd   -..Y@..c<m.@....
    00a0 - d2 a0 80 9c 9f 48 d3 c8-cb 10 79 e7 51 6f 3f d7   .....H....y.Qo?.
    00b0 - 5d 8c f1 6e 80 3b 96 d8-b7 e7 5a 90 2c d8 b9 3c   ]..n.;....Z.,..<
    00c0 - d2 c5 c4 08 9d a6 06 8b-0a 85 86 41 9d 6d 37 63   ...........A.m7c

    Start Time: 1662268008
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
    Session-ID: 4648F5E9B0EA09A9386CD1F8E145822307D76C554E23C649BAEBD9EA1D551D6D
    Session-ID-ctx:
    Resumption PSK: 99CFD3BEFFD6D2DA029ABE3E27E999C843CB492758CD42BAC98CCEE62F7F0EF32DED913B94D6BDEA91B35EAC6712DDDB
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - fb 34 dc b1 cc 2b c6 d3-52 56 11 ae 76 76 80 c3   .4...+..RV..vv..
    0010 - fb c5 2e 18 e0 1e 21 2d-e3 81 0d 52 cd b9 02 81   ......!-...R....
    0020 - 21 d7 13 8f 31 ba 87 7c-f4 cc b6 7c 7f 69 82 2a   !...1..|...|.i.*
    0030 - 7d 10 20 62 93 a0 2d 63-74 2f 48 82 57 17 d8 5f   }. b..-ct/H.W.._
    0040 - 4f 8e 96 30 c5 f8 7e aa-ab fb 66 fe 4b 5f 59 77   O..0..~...f.K_Yw
    0050 - 93 dc a7 c1 6e f5 e8 bd-ee b4 99 b8 4e fe b5 a8   ....n.......N...
    0060 - b4 8c ed 5e 16 53 a6 bb-0d a3 93 fc 86 20 b3 e8   ...^.S....... ..
    0070 - a1 65 ff cb e9 c8 d1 c7-c7 b1 98 88 5f e7 be be   .e.........._...
    0080 - ea 8c 3c cd d5 9b 5e 20-4b 9e 8f b4 9f 3a be 0a   ..<...^ K....:..
    0090 - 2c aa 7f c5 af 86 6d 09-7e 4f 9c 01 48 66 d7 08   ,.....m.~O..Hf..
    00a0 - e0 80 21 a9 36 0f 5b 10-c6 38 da 1d 8b ce 85 9b   ..!.6.[..8......
    00b0 - 4c ea 91 24 2f cb 3f 04-25 5e 16 ed 4b 01 c4 1d   L..$/.?.%^..K...
    00c0 - 6c 4b 4e f1 c9 dc 49 80-f6 10 5a 92 a3 b7 87 b7   lKN...I...Z.....

    Start Time: 1662268008
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

```
## Notas adicionales

## Referencias
https://en.wikipedia.org/wiki/Port_scanner