## Objetivo
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/0505a462ac9beb7412596855df280f6b/shark1.pcapng).

## Solucion
```bash
Abrimos el paquete con wireshark y seguimos el hilo del protocolo tcp, en el stream 5 (827	7.236537	18.222.37.134	192.168.38.104	HTTP	384	HTTP/1.1 200 OK  (text/html)) esta la sig linea:

Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}

La decodificamos con ROT13:
The flag is picoCTF{p33kab00_1_s33_u_deadbeef}
```
picoCTF{p33kab00_1_s33_u_deadbeef}
## Notas adicionales

## Referencias