## Objetivo
What does asm1(0x8be) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/66c927e32f3d7be7a62d13a7c2250943/test.S)

## Solucion
```bash
#Estas dos primeras lineas mueven a la pila ebp
# y despues a ebp se le asigna el valor de esp
<+0>:   push   ebp  
<+1>:   mov    ebp,esp

#Compara si son iguales los datos del primer parametro '0x8be' y '0x71c'
#0x8be==0x71c
<+3>:   cmp    DWORD PTR [ebp+0x8],0x71c
#Si es mas grande el primer parametro con el que se comparo salta a la linea 37
<+10>:  jg     0x512 <asm1+37>
#>>> 0x8be>0x71c
#True
<+12>:  cmp    DWORD PTR [ebp+0x8],0x6cf
<+19>:  jne    0x50a <asm1+29>
<+21>:  mov    eax,DWORD PTR [ebp+0x8]
<+24>:  add    eax,0x3
<+27>:  jmp    0x529 <asm1+60>
<+29>:  mov    eax,DWORD PTR [ebp+0x8]
<+32>:  sub    eax,0x3
<+35>:  jmp    0x529 <asm1+60>

#Compara si son iguales
#0x8be==0x8be
#True
<+37>:  cmp    DWORD PTR [ebp+0x8],0x8be
#Da un salto si no son iguales
<+44>:  jne    0x523 <asm1+54>
#Mueve lo que hay en el primer parametro a eax
<+46>:  mov    eax,DWORD PTR [ebp+0x8]
#Resta lo que hay en eax y '0x3'
#>>> 0x8be-0x3
#2235
<+49>:  sub    eax,0x3
#Da un salto a la linea 60
<+52>:  jmp    0x529 <asm1+60>
<+54>:  mov    eax,DWORD PTR [ebp+0x8]
<+57>:  add    eax,0x3
#Elimina lo que hay en la pila
<+60>:  pop    ebp
#3 y se regresa a la funcion que la llamo
<+61>:  ret


Convertimos lo que nos dio a hexadecimal:
>>> hex(2235)
'0x8bb'

```

## Notas adicionales

## Referencias
https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm