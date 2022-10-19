# Metared International CTF 2022

## Descripcion

My organization has learned about cybersecurity the hard way in recent years.

## Pistas (Si hay)



## Solución

``` Bash

Se abre el archivo con wireshark, se filtra por "telnet" y se busca una cadena similar a la bandera (348	56.435371489	192.168.100.90	192.168.100.72	TELNET	552	Telnet Data ...)

Data: xdsyEP{E2f_9f_Lz1_E9vvd1_2ll2uc}\r\n

Despues utilizamos cyberchef para desencriptar la cadena con ROT8 lo que nos da: flagMX{M2n_9n_Th1_M9ddl1_2tt2ck}

Solo cambiamos los numeros por los que nos corresponden y nos queda asi:
flagMX{M4n_1n_Th3_M1ddl3_4tt4ck}

```

## Referencias