## Objetivo
The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/f9abc386dfb1309e687344783f208b20/need-for-speed).

## Solucion
```bash
──(kali㉿kali)-[~/Downloads]
└─$ gdb need-for-speed
GNU gdb (Debian 12.1-4) 12.1
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from need-for-speed...
(No debugging symbols found in need-for-speed)
(gdb) disassembly main
Undefined command: "disassembly".  Try "help".
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x00000000000005d8  _init
0x0000000000000600  putchar@plt
0x0000000000000610  puts@plt
0x0000000000000620  alarm@plt
0x0000000000000630  __sysv_signal@plt
0x0000000000000640  exit@plt
0x0000000000000650  __cxa_finalize@plt
0x0000000000000660  _start
0x0000000000000690  deregister_tm_clones
0x00000000000006d0  register_tm_clones
0x0000000000000720  __do_global_dtors_aux
0x0000000000000760  frame_dummy
0x000000000000076a  decrypt_flag
0x00000000000007f1  calculate_key
0x000000000000080e  alarm_handler
0x000000000000082f  set_timer
0x000000000000087d  get_key
0x00000000000008ac  print_flag
0x00000000000008d8  header
0x000000000000091a  main
0x0000000000000960  __libc_csu_init
0x00000000000009d0  __libc_csu_fini
0x00000000000009d4  _fini
(gdb) disassembly main
Undefined command: "disassembly".  Try "help".
(gdb) disassemble main
Dump of assembler code for function main:
   0x000000000000091a <+0>:     push   %rbp
   0x000000000000091b <+1>:     mov    %rsp,%rbp
   0x000000000000091e <+4>:     sub    $0x10,%rsp
   0x0000000000000922 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000000000000925 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000000000000929 <+15>:    mov    $0x0,%eax
   0x000000000000092e <+20>:    call   0x8d8 <header>
   0x0000000000000933 <+25>:    mov    $0x0,%eax
   0x0000000000000938 <+30>:    call   0x82f <set_timer>
   0x000000000000093d <+35>:    mov    $0x0,%eax
   0x0000000000000942 <+40>:    call   0x87d <get_key>
   0x0000000000000947 <+45>:    mov    $0x0,%eax
   0x000000000000094c <+50>:    call   0x8ac <print_flag>
   0x0000000000000951 <+55>:    mov    $0x0,%eax
   0x0000000000000956 <+60>:    leave  
   0x0000000000000957 <+61>:    ret    
End of assembler dump.
(gdb) break main
Breakpoint 1 at 0x91e
(gdb) info breakpoints
Num     Type           Disp Enb Address            What
1       breakpoint     keep y   0x000000000000091e <main+4>

(gdb) run
Starting program: /home/kali/Downloads/need-for-speed 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000055555540091e in main ()
(gdb) disassemble main
Dump of assembler code for function main:                                                                           
   0x000055555540091a <+0>:     push   %rbp                                                                         
   0x000055555540091b <+1>:     mov    %rsp,%rbp                                                                    
=> 0x000055555540091e <+4>:     sub    $0x10,%rsp                                                                   
   0x0000555555400922 <+8>:     mov    %edi,-0x4(%rbp)                                                              
   0x0000555555400925 <+11>:    mov    %rsi,-0x10(%rbp)                                                             
   0x0000555555400929 <+15>:    mov    $0x0,%eax                                                                    
   0x000055555540092e <+20>:    call   0x5555554008d8 <header>                                                      
   0x0000555555400933 <+25>:    mov    $0x0,%eax                                                                    
   0x0000555555400938 <+30>:    call   0x55555540082f <set_timer>                                                   
   0x000055555540093d <+35>:    mov    $0x0,%eax                                                                    
   0x0000555555400942 <+40>:    call   0x55555540087d <get_key>                                                     
   0x0000555555400947 <+45>:    mov    $0x0,%eax                                                                    
   0x000055555540094c <+50>:    call   0x5555554008ac <print_flag>                                                  
   0x0000555555400951 <+55>:    mov    $0x0,%eax                                                                    
   0x0000555555400956 <+60>:    leave                                                                               
   0x0000555555400957 <+61>:    ret                                                                                 
End of assembler dump.                                                                                              
(gdb) call (int) get_key()                                                                                          
Creating key...                                                                                                     
Finished                                                                                                            
$1 = 9                                                                                                              
(gdb) call (int) print_flag()                                                                               
Printing flag:                                                                                                      
PICOCTF{Good job keeping bus #190ca38b speeding along!}                                                             
$2 = 56                                                                                                             
(gdb) Quit                                                                                                          
(gdb)  

```
PICOCTF{Good job keeping bus #190ca38b speeding along!}  
## Notas adicionales

## Referencias