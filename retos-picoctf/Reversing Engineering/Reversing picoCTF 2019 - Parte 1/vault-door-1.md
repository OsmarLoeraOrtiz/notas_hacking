## Objetivo
This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java)

## Solucion
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ cat txt | sort                                            
               password.charAt(00)  == 'd' &&
               password.charAt(01)  == '3' &&
               password.charAt(02)  == '5' &&
               password.charAt(03)  == 'c' &&
               password.charAt(04)  == 'r' &&
               password.charAt(05)  == '4' &&
               password.charAt(06)  == 'm' &&
               password.charAt(07)  == 'b' &&
               password.charAt(08)  == 'l' &&
               password.charAt(09)  == '3' &&
               password.charAt(10) == '_' &&
               password.charAt(11) == 't' &&
               password.charAt(12) == 'H' &&
               password.charAt(13) == '3' &&
               password.charAt(14) == '_' &&
               password.charAt(15) == 'c' &&
               password.charAt(16) == 'H' &&
               password.charAt(17) == '4' &&
               password.charAt(18) == 'r' &&
               password.charAt(19) == '4' &&
               password.charAt(20) == 'c' &&
               password.charAt(21) == 'T' &&
               password.charAt(22) == '3' &&
               password.charAt(23) == 'r' &&
               password.charAt(24) == '5' &&
               password.charAt(25) == '_' &&
               password.charAt(26) == 'f' &&
               password.charAt(27) == '6' &&
               password.charAt(28) == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(30) == 'f' &&
               password.charAt(31) == '4'
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ cat txt | sort | awk '{print($3)}'| tr -d "'" | tr -d "\n"
d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4   

```
picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4}
## Notas adicionales

## Referencias