# Nice netcat...


## Objetivo
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 22342`, but it doesn't speak English..

## Solucion
```bash
┌──(kali㉿kali)-[~/hacking]
└─$ nc mercury.picoctf.net 22342
112
105
99
111
67
84
70
123
103
48
48
100
95
107
49
116
116
121
33
95
110
49
99
51
95
107
49
116
116
121
33
95
53
102
98
53
101
53
49
100
125
10
┌──(kali㉿kali)-[~/hacking]
└─$ python
>>> nums = [112,105,99,111,67,84,70,123,103,48,48,100,95,107,49,116,116,121,33,95,110,49,99,51,95,107,49,116,116,121,33,95,53,102,98,53,101,53,49,100,125,10]
>>> flag = ""
>>> for x in nums:
...      flag += chr(x) 
>>> print(flag)
>>> picoCTF{g00d_k1tty!_n1c3_k1tty!_5fb5e51d}


```
picoCTF{g00d_k1tty!_n1c3_k1tty!_5fb5fb51d}
## Notas adicionales

## Referencias