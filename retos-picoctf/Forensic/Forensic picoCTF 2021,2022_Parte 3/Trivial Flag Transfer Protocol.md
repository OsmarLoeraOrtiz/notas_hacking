## Objetivo
Figure out how they moved the [flag](https://mercury.picoctf.net/static/cc6074838ede2edf9f805fd2b58bdc58/tftp.pcapng).
## Solucion
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ wireshark tftp.pcapng
 ** (wireshark:6122) 16:44:50.532663 [GUI WARNING] -- QXcbConnection: XCB error: 3 (BadWindow), sequence: 608, resource id: 21194603, major code: 40 (TranslateCoords), minor code: 0
 ** (wireshark:6122) 16:46:03.074855 [GUI WARNING] -- FIX Add drag reordering to UAT dialog
 ** (wireshark:6122) 16:46:51.852111 [GUI WARNING] -- QXcbConnection: XCB error: 3 (BadWindow), sequence: 7950, resource id: 21198072, major code: 40 (TranslateCoords), minor code: 0
 ** (wireshark:6122) 16:48:31.509210 [GUI WARNING] -- QXcbConnection: XCB error: 3 (BadWindow), sequence: 18961, resource id: 21323480, major code: 40 (TranslateCoords), minor code: 0
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
'instructions(1).txt'   picture1.bmp      'picture3(1).bmp'  'plan(1)'          tftp.pcapng
 instructions.txt      'picture2(1).bmp'   picture3.bmp      'program(1).deb'
'picture1(1).bmp'       picture2.bmp       plan               program.deb
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ cat instructions.txt | tr [A-Z] [N-ZA-m]
TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ file plan                   
plan: ASCII text
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ cat plan                                
VHFRQGURCEBTENZNAQUVQVGJVGU-QHRQVYVTRAPR.PURPXBHGGURCUBGBF
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ cat plan | tr [A-Z] [N-ZA-m]
IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ open picture1.bmp 
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ dpkg -I program.deb 
 new Debian package, version 2.0.
 size 138310 bytes: control archive=1250 bytes.
     826 bytes,    18 lines      control              
    1184 bytes,    17 lines      md5sums              
 Package: steghide
 Source: steghide (0.5.1-9.1)
 Version: 0.5.1-9.1+b1
 Architecture: amd64
 Maintainer: Ola Lundqvist <opal@debian.org>
 Installed-Size: 426
 Depends: libc6 (>= 2.2.5), libgcc1 (>= 1:4.1.1), libjpeg62-turbo (>= 1:1.3.1), libmcrypt4, libmhash2, libstdc++6 (>= 4.9), zlib1g (>= 1:1.1.4)
 Section: misc
 Priority: optional
 Description: A steganography hiding tool
  Steghide is steganography program which hides bits of a data file
  in some of the least significant bits of another file in such a way
  that the existence of the data file is not visible and cannot be proven.
  .
  Steghide is designed to be portable and configurable and features hiding
  data in bmp, wav and au files, blowfish encryption, MD5 hashing of
  passphrases to blowfish keys, and pseudo-random distribution of hidden bits
  in the container data.
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ sudo dpkg -I steghide     
[sudo] password for kali: 
dpkg-deb: error: failed to read archive 'steghide': No such file or directory
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ sudo dpkg -I program.deb 
 new Debian package, version 2.0.
 size 138310 bytes: control archive=1250 bytes.
     826 bytes,    18 lines      control              
    1184 bytes,    17 lines      md5sums              
 Package: steghide
 Source: steghide (0.5.1-9.1)
 Version: 0.5.1-9.1+b1
 Architecture: amd64
 Maintainer: Ola Lundqvist <opal@debian.org>
 Installed-Size: 426
 Depends: libc6 (>= 2.2.5), libgcc1 (>= 1:4.1.1), libjpeg62-turbo (>= 1:1.3.1), libmcrypt4, libmhash2, libstdc++6 (>= 4.9), zlib1g (>= 1:1.1.4)
 Section: misc
 Priority: optional
 Description: A steganography hiding tool
  Steghide is steganography program which hides bits of a data file
  in some of the least significant bits of another file in such a way
  that the existence of the data file is not visible and cannot be proven.
  .
  Steghide is designed to be portable and configurable and features hiding
  data in bmp, wav and au files, blowfish encryption, MD5 hashing of
  passphrases to blowfish keys, and pseudo-random distribution of hidden bits
  in the container data.
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ steghide picture1.bmp 
Command 'steghide' not found, but can be installed with:
sudo apt install steghide
Do you want to install it? (N/y)y
sudo apt install steghide
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libmcrypt4 libmhash2
Suggested packages:
  libmcrypt-dev mcrypt
The following NEW packages will be installed:
  libmcrypt4 libmhash2 steghide
0 upgraded, 3 newly installed, 0 to remove and 1012 not upgraded.
Need to get 311 kB of archives.
After this operation, 907 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://kali.download/kali kali-rolling/main amd64 libmcrypt4 amd64 2.5.8-7 [72.6 kB]
Get:2 http://kali.download/kali kali-rolling/main amd64 libmhash2 amd64 0.9.9.9-9 [94.2 kB]
Get:3 http://kali.download/kali kali-rolling/main amd64 steghide amd64 0.5.1-15 [144 kB]
Fetched 311 kB in 2s (156 kB/s)     
Selecting previously unselected package libmcrypt4.
(Reading database ... 340621 files and directories currently installed.)
Preparing to unpack .../libmcrypt4_2.5.8-7_amd64.deb ...
Unpacking libmcrypt4 (2.5.8-7) ...
Selecting previously unselected package libmhash2:amd64.
Preparing to unpack .../libmhash2_0.9.9.9-9_amd64.deb ...
Unpacking libmhash2:amd64 (0.9.9.9-9) ...
Selecting previously unselected package steghide.
Preparing to unpack .../steghide_0.5.1-15_amd64.deb ...
Unpacking steghide (0.5.1-15) ...
Setting up libmhash2:amd64 (0.9.9.9-9) ...
Setting up libmcrypt4 (2.5.8-7) ...
Setting up steghide (0.5.1-15) ...
Processing triggers for libc-bin (2.35-3) ...
Processing triggers for man-db (2.10.2-1) ...
Processing triggers for kali-menu (2022.3.1) ...
Scanning processes...                                                                                               
Scanning processor microcode...                                                                                     
Scanning linux images...                                                                                            

Running kernel seems to be up-to-date.

Failed to check for processor microcode upgrades.

No services need to be restarted.

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ steghide picture1.bmp
steghide: unknown command "picture1.bmp".
steghide: type "steghide --help" for help.
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ steghide --extract -sf  picture1.bmp
Enter passphrase: 
steghide: could not extract any data with that passphrase!
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ steghide --extract -sf  picture2.bmp
Enter passphrase: 
steghide: could not extract any data with that passphrase!
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ steghide --extract -sf  picture3.bmp
Enter passphrase: 
wrote extracted data to "flag.txt".
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ cat flag.txt                
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ 


```
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
## Notas adicionales
Los archivos se descargan de wireshark, en la pestaña de file y despues en extract object 
## Referencias