## Objetivo
This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/a4018cec1446761cb2e8cce05db925fa/VaultDoor3.java)
## Solucion
```bash
import java.util.*;

public class VaultDoor3 {
    public static void main(String args[]) {
 
    char[] buffer = new char[32];
    int i;
    String password = "jU5t_a_sna_3lpm12g94c_u_4_m7ra41";
    for (i=0; i<8; i++) {
        buffer[i] = password.charAt(i);
    }
    for (; i<16; i++) {
        buffer[i] = password.charAt(23-i);
    }
    for (; i<32; i+=2) {
        buffer[i] = password.charAt(46-i);
    }
    for (i=31; i>=17; i-=2) {
        buffer[i] = password.charAt(i);
    }
    String s = new String(buffer);
    System.out.println(s+"");
    }
}

jU5t_a_s1mpl3_an4gr4m_4_u_c79a21


```
picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_c79a21}
## Notas adicionales

## Referencias