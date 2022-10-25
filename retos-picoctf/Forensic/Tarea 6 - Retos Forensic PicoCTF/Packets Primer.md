## Objetivo
Download the packet capture file and use packet analysis software to find the flag.

-   [Download packet capture](https://artifacts.picoctf.net/c/199/network-dump.flag.pcap)
## Solucion
```bash
Abrimos el paquete con wireshark y seguimos el hilo TCP y en el stream 0 esta la bandera 
p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ c e c c a a 7 f }
```

## Notas adicionales

## Referencias