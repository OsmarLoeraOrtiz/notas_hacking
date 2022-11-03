## Objetivo
This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/834acd392e0964a41f05790655a994b9/VaultDoor4.java)
## Solucion
```bash
Copiamos el arreglo de bystes y lo decodificamos metiendolo a un arreglo en javascript:
String.fromCharCode(106 , 85  , 53  , 116 , 95  , 52  , 95  , 98,0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f, 0142, 0131, 0164, 063 , 0163, 0137, 0146, 064) + ['a' , '8' , 'c' , 'd' , '8' , 'f' , '7' , 'e'].join('')
jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e

```
picoCTF{jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e}
## Notas adicionales

## Referencias