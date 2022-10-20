## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Solucion
```bash
Abrimos el archivo con wireshark y seguimos el stream del protocolo UDP y despues buscamos algo parecido a la bandera. La bandera esta en el stream 6, y es la siguiente:
picoCTF{StaT31355_636f6e6e}
```

## Notas adicionales

## Referencias