# 


## Objetivo
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/e38f6a5b69b45d21e33cf7281d8c2531/Addadshashanammu.zip)

## Solucion
```bash
┌──(kali㉿kali)-[~/hacking]
└─$ unzip Addadshashanammu.zip

"Dar tab hasta el ultimo directorio."

┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$cat fang-of-haynekhtnamet                                                     GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.0                                      8 T                    t                                                         8                                    #             T      T           1             t      t      $                              D   o             N                                                   V             `      `                                    ^   o                                  k   o                                               z                     B                                                                                                                                                    0      0                       ...        
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ strings fang-of-haynekhtnamet | grep pico
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_f3553887}

┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ 

```
picoCTF{l3v3l_up!_t4k3_4_r35t!_f3553887}
## Notas adicionales

## Referencias