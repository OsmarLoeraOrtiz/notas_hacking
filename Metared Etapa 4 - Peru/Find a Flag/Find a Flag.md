# Nombre del reto
### FInd a Flag (general skills)	
## Objetivo
```
Unzip this [archive](https://drive.google.com/file/d/15pFs7BTOuJ4jrHZOAHNXfPWunY0K9fGl/view?usp=sharing) and find the file named 'oliver_twist.txt'
```
## Solucion
``` shell 
┌──(anitars㉿kali)-[~/…/great/great_author/acceptable_books/more_books]
└─$ cd ..
                                                                          
┌──(anitars㉿kali)-[~/…/MetaRed-Peru/great/great_author/acceptable_books]
└─$ cd ..
                                                                          
┌──(anitars㉿kali)-[~/…/picoCTF/MetaRed-Peru/great/great_author]
└─$ cd adequate_books  
                                                                          
┌──(anitars㉿kali)-[~/…/MetaRed-Peru/great/great_author/adequate_books]
└─$ cd more_books    
                                                                          
┌──(anitars㉿kali)-[~/…/great/great_author/adequate_books/more_books]
└─$ ls -a
.  ..  1023.txt.utf-8  .secret
                                                                          
┌──(anitars㉿kali)-[~/…/great/great_author/adequate_books/more_books]
└─$ cd .secret   
                                                                          
┌──(anitars㉿kali)-[~/…/great_author/adequate_books/more_books/.secret]
└─$ ls   
deeper_secrets
                                                                          
┌──(anitars㉿kali)-[~/…/great_author/adequate_books/more_books/.secret]
└─$ cd deeper_secrets 
                                                                          
┌──(anitars㉿kali)-[~/…/adequate_books/more_books/.secret/deeper_secrets]
└─$ ls
deepest_secrets
                                                                          
┌──(anitars㉿kali)-[~/…/adequate_books/more_books/.secret/deeper_secrets]
└─$ cd deepest_secrets 
                                                                          
┌──(anitars㉿kali)-[~/…/more_books/.secret/deeper_secrets/deepest_secrets]
└─$ ls
Oliver_Twist.txt
                                                                          
┌──(anitars㉿kali)-[~/…/more_books/.secret/deeper_secrets/deepest_secrets]
└─$ cat Oliver_Twist.txt 
fl@g{Ch@rRl3$_D1cK3N$}
                                                                          
┌──(anitars㉿kali)-[~/…/more_books/.secret/deeper_secrets/deepest_secrets]
└─$ 


Descargamos lo marcado y buscamos la el documento que nos dice el objetivo, lo encontramos y encontramos la bandera.
```
## Referencias
```

```
