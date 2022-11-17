## Objetivo
What does asm2(0xb,0x2e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S)
## Solucion
```bash
stack
[]
[]
[0xb]<-[ebp-0x8]
[0x2e]<-[ebp-0x4]
[ebp]<-esp<-ebp
[ret]<-[ebp+0x4]
[0xb]<-[ebp+0x8]
[0x2e]<-[ebp+0xc]

registers[eax]
[0xb]

<+0>:   push   ebp
<+1>:   mov    ebp,esp
#Se crean 4 espacios en la memoria
<+3>:   sub    esp,0x10
#Lo que hay en el espacio ebp+0xc lo manda a eax
<+6>:   mov    eax,DWORD PTR [ebp+0xc]
#Lo que hay en eax lo mueve a la posicion ebp-0x4 de la pila
<+9>:   mov    DWORD PTR [ebp-0x4],eax
#Lo que hay en el espacio ebp+0x8 lo manda a eax
<+12>:  mov    eax,DWORD PTR [ebp+0x8]
#Lo que hay en eax lo mueve a la posicion ebp-0x4 de la pila
<+15>:  mov    DWORD PTR [ebp-0x8],eax
#hace un salto a la linea asm+28
<+18>:  jmp    0x509 <asm2+28>
<+20>:  add    DWORD PTR [ebp-0x4],0x1       
<+24>:  sub    DWORD PTR [ebp-0x8],0xffffff80
#Compara si lo que hay en la posicion ebp-0x8 es == a 0x63f3
<+28>:  cmp    DWORD PTR [ebp-0x8],0x63f3
#si no son iguales se regresa a la linea 20
<+35>:  jle    0x501 <asm2+20>
<+37>:  mov    eax,DWORD PTR [ebp-0x4]

<+40>:  leave  
<+41>:  ret  

#Script
def asm2(arg1, arg2):
#asm2:
    #<+0>:  push   ebp
    #<+1>:  mov    ebp,esp
    #<+3>:  sub    esp,0x10

    #<+6>:  mov    eax,DWORD PTR [ebp+0xc]
    eax = arg2

    #<+9>:  mov    DWORD PTR [ebp-0x4],eax
    local1 = eax

    #<+12>: mov    eax,DWORD PTR [ebp+0x8]
    eax = arg1

    #<+15>: mov    DWORD PTR [ebp-0x8],eax
    local2 = eax

    #<+18>: jmp    0x509 <asm2+28>
    #<+20>: add    DWORD PTR [ebp-0x4],0x1
    #<+24>: sub    DWORD PTR [ebp-0x8],0xffffff80
    #<+28>: cmp    DWORD PTR [ebp-0x8],0x63f3
    #<+35>: jle    0x501 <asm2+20>
    while(local2 <= 0x63f3):
	    local1 = (local1 + 1) & 0xffffffff              #This truncates the result to 32 bits.
        local2 = (local2 - 0xffffff80)  & 0xffffffff    #This truncates the result to 32 bits.           

    #<+37>: mov    eax,DWORD PTR [ebp-0x4]
    #<+40>: leave
    #<+41>: ret
    return hex(local1)

bandera: 0xf6



```

## Notas adicionales

## Referencias