## Objetivo
What will asm4("picoCTF_f97bb") return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/76ef117df9226a8a9306a8865b14068e/test.S)
## Solucion
```bash
#chal.s
.intel_syntax noprefix
.global asm4
asm4:
        push   ebp
        mov    ebp,esp
        push   ebx
        sub    esp,0x10
        mov    DWORD PTR [ebp-0x10],0x27a
        mov    DWORD PTR [ebp-0xc],0x0
        jmp    asm4+27
        add    DWORD PTR [ebp-0xc],0x1
        mov    edx,DWORD PTR [ebp-0xc]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        test   al,al
        jne    asm4+23
        mov    DWORD PTR [ebp-0x8],0x1
        jmp    asm4+138
        mov    edx,DWORD PTR [ebp-0x8]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        movsx  edx,al
        mov    eax,DWORD PTR [ebp-0x8]
        lea    ecx,[eax-0x1]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,ecx
        movzx  eax,BYTE PTR [eax]
        movsx  eax,al
        sub    edx,eax
        mov    eax,edx
        mov    edx,eax
        mov    eax,DWORD PTR [ebp-0x10]
        lea    ebx,[edx+eax*1]
        mov    eax,DWORD PTR [ebp-0x8]
        lea    edx,[eax+0x1]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        movsx  edx,al
        mov    ecx,DWORD PTR [ebp-0x8]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,ecx
        movzx  eax,BYTE PTR [eax]
        movsx  eax,al
        sub    edx,eax
        mov    eax,edx
        add    eax,ebx
        mov    DWORD PTR [ebp-0x10],eax
        add    DWORD PTR [ebp-0x8],0x1
        mov    eax,DWORD PTR [ebp-0xc]
        sub    eax,0x1
        cmp    DWORD PTR [ebp-0x8],eax
        jl     asm4+51
        mov    eax,DWORD PTR [ebp-0x10]
        add    esp,0x10
        pop    ebx
        pop    ebp
        ret 

#solve.c
#include <stdio.h>

int main(){
        printf("Flag: 0x%x\n", asm4("picoCTF_f97bb"));
}
   
┌──(kali㉿kali)-[~/Downloads]
└─$ gcc -m32 -c solve.c -o solve.o
solve.c: In function ‘main’:
solve.c:4:32: warning: implicit declaration of function ‘asm4’ [-Wimplicit-function-declaration]
    4 |         printf("Flag: 0x%x\n", asm4("picoCTF_f97bb"));
      |                                ^~~~
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ gcc -m32 -c solve.c -o solve.o -w
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ gcc -m32 -o a.out solve.o chal.o 
/usr/bin/ld: warning: chal.o: missing .note.GNU-stack section implies executable stack
/usr/bin/ld: NOTE: This behaviour is deprecated and will be removed in a future version of the linker

┌──(kali㉿kali)-[~/Downloads]
└─$ ./a.out 
Flag: 0x265
```

## Notas adicionales

## Referencias