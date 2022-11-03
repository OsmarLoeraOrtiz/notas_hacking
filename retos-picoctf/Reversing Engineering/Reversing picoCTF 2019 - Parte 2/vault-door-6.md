## Objetivo
This vault uses an XOR encryption scheme. The source code for this vault is here: [VaultDoor6.java](https://jupiter.challenges.picoctf.org/static/86e94cc555b2ca7375424c884ef581a6/VaultDoor6.java)

## Solucion
```bash
public class exp {

        public static void main(String[] args) {

                byte[] myBytes = {
                 0x3b, 0x65, 0x21, 0xa , 0x38, 0x0 , 0x36, 0x1d,
                 0xa , 0x3d, 0x61, 0x27, 0x11, 0x66, 0x27, 0xa ,
                 0x21, 0x1d, 0x61, 0x3b, 0xa , 0x2d, 0x65, 0x27,
                    0xa , 0x66, 0x36, 0x30, 0x67, 0x6c, 0x64, 0x6c,
                };

                for (int i=0; i<32; i++) {
                        System.out.print((char)(myBytes[i] ^ 0x55));
                }

        }

}

Al correr el programa obtenemos:
n0t_mUcH_h4rD3r_tH4n_x0r_3ce2919


```
picoCTF{n0t_mUcH_h4rD3r_tH4n_x0r_3ce2919}
## Notas adicionales

## Referencias