
## Objetivo
Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.

## Solucion
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ sstv -d message.wav -o result.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [##################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ open result.png                        
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ picoCTF{beep_boop_im_in_space}   

```

## Notas adicionales

## Referencias